## Azure CLI Commands Used

```bash
# Set subscription
az account set --subscription f0c3bcdd-5ce2-4fa0-8cf3-41559747512b

# Create resource group
az group create --name xfusion-rg --location westus

# Create SSH key
az sshkey create \
  --name xfusion-kp \
  --resource-group xfusion-rg \
  --location westus

# Verify SSH key
az sshkey show \
  --name xfusion-kp \
  --resource-group xfusion-rg
