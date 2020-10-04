# Run a Ubiquiti Unifi Controller on Azure Container Instances

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fdanieletten%2Funifi-controller-on-azure%2Fmain%2Fazuredeploy.json)

Do you want to use a docker container to host your Unifi Controller?

Did you take a look at an Azure Web App to host you Unifi Controller, but noticed that you couldn't setup the required ports?

Host your Ubiquiti controller on an Azure Container Instance will do the trick!

## Azure template

As you see I have added on the top of this page the option to use my template to deploy this solution in your Azure environment.
This will install the [linuxserver/unificontroller](https://hub.docker.com/r/linuxserver/unifi-controller). The Unifi controller will be deployed on a Container Instance in Azure and uses an Azure file share to store it's configuration data.

## Things to do after deployment

After you have deployed the ARM template to Azure you'll only need to do 2 things

1. Add your SSL certificate to /unifi/cert in the storage accounts fileshare
2. Configure the controller

### Access the controller

When the deployment is finished navigate in the Azure portal to the created Resource Group and select your Container Instance, in this case heyazureguy-2020.

![Resource Group](/images/azure-portal-resource-group.png)

When you have clicked on the Container Instance, you'll see the FQDN of your Unifi Controller. Copy the URL and past this in your browser, make sure that you select port 8080 to reach the setup page. In this case the URL would be [http://heyazureguy.westeurope.azurecontainer.io:8080](#blank) or [https://heyazureguy.westeurope.azurecontainer.io:8443](#blank)

![Resource Group](/images/azure-portal-container-instance.png)
