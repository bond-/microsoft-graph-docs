<!-- markdownlint-disable MD002 MD041 -->

The next step is to use the Azure Data Factory to create a pipeline to extract the data from Microsoft 365 to the Azure Storage account using Microsoft Graph data connect.

## Create an Azure Data Factory pipeline

1. Open a browser and navigate to your [Azure Portal](https://portal.azure.com/).

1. Login using an account with **Global Administrator** rights to your Azure and Microsoft 365 tenants.

    > [!NOTE]
    > Keep track of the user you are using in this step as you will need to switch to the other user you granted the **Global Administrator** role and that has multi-factor authentication enabled on their account in a later step.

1. Select **Create a resource** from the sidebar navigation.

1. Find the **Data Factory** resource type and use the following values to create it, then select **Create**:

    1. **Name**: dfM365toBlobStorage
    2. **Subscription**: select your Azure subscription
    3. **Resource group**: GraphDataConnect
    4. **Version**: V2
    5. **Location**: pick an Azure region in the same region as your Microsoft 365 region

    ![Azure-ADF-Create](images/data-connect-adf-create.png)

1. Once the Azure Data Factory resource is created, select the **Author and Monitor** tile to launch the Azure Data Factory full screen editor.

    ![Azure-ADF-Auth-and-Mon](images/data-connect-adf-auth-and-mon.png)

1. Switch from the **Overview** to the **Manage** experience by selecting it from the left-hand navigation:

    ![Azure-ADF-Manage](images/data-connect-adf-manage.png)

1. **Optional step**. By default, the Azure Data Factory will use an Integration Runtime that is auto resolving the region. As the Microsoft Graph Data Connect requires that your source and destination, and integration runtime to exist in the same Microsoft 365 region, it is recommended that you create a new Integration Runtime with a fixed region.

    1. Select **Integration runtimes** > **New**.
    1. Select **Azure**, **Self-Hosted** and select **Continue**.

    ![Azure-ADF-Runtime](images/data-connect-adf-runtime.png)

    1. Select **Azure** for network environment and select **Continue**.

    ![Azure-ADF-Network](images/data-connect-adf-network.png)

    1. Use the following details to complete the form on the final screen and then select Create:

        - **Name**: name of your integration runtime
        - **Description**: enter a description
        - **Region**: select the region that matches your Microsoft 365 region

        ![Azure-ADF-Runtime-Setup](images/data-connect-adf-runtime-setup.png)

1. Switch from the **Manage** to the **Author** experience by selecting it from the left-hand navigation and create a new pipeline by selecting the **plus** icon, then **pipeline**:

    ![Azure-ADF-Pipeline-Create](images/data-connect-adf-pipeline-create.png)

    - Drag the **Copy Data** activity from the **Move and Transform** section onto the design surface:

    ![Azure-ADF-Pipeline-Copy-Data](images/data-connect-adf-pipeline-copy-data.png)

    - Select the activity in the designer.
    - In the activity editor pane below the designer, select the **Source** tab, then select **New**.
    - Locate the dataset **Microsoft 365**, select it and then select the **Continue** button.

    ![Azure-ADF-Pipeline-Dataset](images/data-connect-adf-pipeline-dataset.png)

    - The designer will create a new tab for the Microsoft 365 connector. Select the **Connection** tab in the connector's editor, then the **New** button.
    - In the dialog that appears, enter the previously created Azure AD application's **Application ID** and **Password** in the **Service principal ID** and **Service principal key** fields, then select **Finish**.

    > [!TIP]
    > If you created a dedicated Integration Runtime, select it in the Connect via integration runtime dropdown.

    ![Azure-ADF-](images/data-connect-adf-linked-service.png)

    - After creating the Microsoft 365 connection, for the **Table** field, select **BasicDataSet_v0.Message_v0**.

    ![Azure-ADF-Pipeline-Dataset-Table](images/data-connect-adf-pipeline-dataset-table.png)

    - Switch from **Office365Table** to **Pipeline > Source**. Use the following values for the **Date filter**.

        - **Column Name**: CreatedDateTime
        - **Start time (UTC)**: select a date sometime prior to the current date
        - **End time (UTC)**: select the current date

    - Select the **Source** tab and then select **Import schema**.

    ![Azure-ADF-Pipeline-Configure-Schema](images/data-connect-adf-configure-schema.png)

    - With the source configured for your **copy data** activity, now configure the **sink**, or the location where data will be stored.
    - Select the tab in the designer for your pipeline.
    - Select the **copy data** activity, then select the sink tab.
    - Select the **New** button, select **Azure Blob Storage**, and then select the **Continue** button.

    ![Azure-ADF-Pipeline-Configure-Storage-Account](images/data-connect-adf-configure-storage.png)

    - Select **Binary** as the format for the data and then select the **Continue** button.

    ![Azure-ADF-Pipeline-Configure-Storage-File-Format](images/data-connect-adf-configure-sa-format.png)

    - Give the dataset the name __M365JsonFile__ and create new linked service if it does not exist already.

    ![Azure-ADF-Pipeline-Configure-Linked-Service](images/data-connect-adf-configure-linked-service.png)

    - Select the **Connection** tab, then select **New**.
    - Set the following values in the dialog, then select **Finish**:

        - **Authentication method**: Service principal
        - **Azure subscription**: Select all
        - **Storage account name**: {tenantid}gdcdump
        This is the storage account created earlier in this exercise.
        - **Tenant**: enter the ID of your Azure tenant
        - **Service principal ID**: enter the ID of the Azure AD application you previously created
        - **Service principal key**: enter the hashed key of the Azure AD application you previously created

        > [!NOTE]
        > If you created a dedicated Integration Runtime, select it in the Connect via integration runtime dropdown.

        ![Azure-ADF-Pipeline-Configure-LS-Settings](images/data-connect-adf-ls-config.png)

    - Next to the **File path** field, select **Browse**.
    - Select the name of the storage container you created previously.

      ![Azure-ADF-Pipeline-Configure-SA-File-Path](images/data-connect-adf-sa-fp-config.png)

    - Ensure the **File format** is set to **Binary** format.
    - Set the **File pattern** to **Set of objects**.

1. With the pipeline created, select the **Validate All** button at the top of the designer.

1. After validating (and fixing any issues that were found), select the **Publish All** button at the top of the designer.

## Execute the Azure Data Factory Pipeline

With the pipeline created, now it is time to execute it.

> [!NOTE]
> It can take several minutes for the consent request to appear and it is not uncommon for the entire process (start, requesting consent and after approving the consent completing the pipeline run) to take over 40 minutes.

1. In the Azure Data Factory designer, with the pipeline open, select **Add trigger > Trigger Now**:

    ![Azure-ADF-Pipeline-Execute-Trigger](images/data-connect-adf-execute-trigger.png)

1. After starting the job, from the sidebar menu, select **Monitor** to view current running jobs:

1. Locate the pipeline run you just started in the list. In the **Actions** column, select the **View Activity Runs** icon:

1. On the **Activity Runs** screen, you will see a list of all the activities that are running in this pipeline. Our pipeline only has one activity that should show as currently In Progress.

    ![Azure-ADF-Pipeline-Execute-Monitor-Activity](images/data-connect-adf-pipeline-activity.png)

1. While the status may show as In Progress, the request may be paused internally as the request for access to the data in Microsoft 365 may need to be approved. You can see if this is the case by selecting the **Details** icon in the **Actions** column.

1. In the **Details** screen, look for the status of the pipeline activity as highlighted in the following image. In this case you can see it is in a state of **RequestingConsent**:

    ![Azure-ADF-Pipeline-Execute-Wait-for-Request-Approval](images/data-connect-adf-wait-for-approval.png)

1. At this point, the activity run is internally paused until someone manually approves the consent request.
