<!-- markdownlint-disable MD002 MD041 -->

In this exercise you will create, execute, and approve an Azure Data Factory pipeline to extract data from Microsoft 365 to an Azure Storage Blob for additional processing.

## Create a Microsoft Azure Active Directory application registration

The first step is to create an Azure AD application that will be used as the security principal to run the data extraction process.

1. Open a browser and go to your [Azure Portal](https://portal.azure.com/).

1. Sign in using an account with **Global Administrator** rights to your Azure and Microsoft 365 tenants.

1. Select **Azure Active Directory** (Azure AD) from the sidebar navigation.

1. On the Azure AD Overview page, select **App registrations** from the **Manage** section of the menu.

1. Select the **New application registration** button:

    ![AAD-App-Registration](images/data-connect-azure-aad-app-reg.png)

1. Use the following values to create a new Azure AD application and select **Register**:

   - **Name**: Microsoft Graph Data Connect Data Transfer
   - **Supported account types**: Accounts in this organizational directory only.
   - **Redirect URI**: Leave the default values.

    ![AAD-App-Registration-Redirect-URI](images/data-connect-aad-redirect-uri.png)

1. Locate the **Application (client) ID** and copy it as you will need it later in this tutorial. This will be referred to as the service principal ID.

1. Locate the **Directory (tenant) ID** and copy it as you will need it later in this tutorial. This will be referred to as the tenant ID.

1. Select **Certificates and secrets** under **Manage** in the sidebar navigation.

1. Select the **New client secret button**. Set *Description* to _Never expires_, set **Expires** to _Never_ and choose **Add**.

    > [!IMPORTANT]
    > You can choose different values for **Description** and **Expires** if you like, but ensure you keep a copy of the name and the hashed key after it is saved as the hashed value will never be shown again and you will need to create a new key as it is needed later in the tutorial.

    ![AAD-App-Registration-Certs-and-Secrets](images/data-connect-aad-certs-secrets.png)

    This will be referenced as the service principal key.

1. Using the sidebar navigation for the application, select **Owners**.

1. Verify that your account is listed as an owner for the application. If it isn't listed as an owner, add it.

    ![AAD-App-Registration](images/data-connect-aad-app-owners.png)
