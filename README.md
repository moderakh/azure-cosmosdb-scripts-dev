# Azure Cosmos DB Scripts for Dev
This repo contains helpful scripts which are useful when developing against Azure Cosmos DB Service.


## Requirements:
1. bash
2. azure-cli (https://docs.microsoft.com/en-us/cli/azure/install-azure-cli)

Note: I use this on MacOS. It should work on non-MacOS environment too, but I have only used and tested this on MacOS.

clone the repo
```bash
git clone https://github.com/moderakh/azure-cosmosdb-scripts-dev.git
cd azure-cosmosdb-scripts-dev
```

# (import-emulator-cert-to-java-trust-store.sh) Import Emulator Self Sign cert in MacOS or Linux

Start the emulator 

run command targetting emulator cooridanates to import cert
```bash
bash import-emulator-cert-to-java-trust-store.sh --host localhost --port 8081
```


# (az_delete_cosmosdb_databases.sh) Delete all databases in dev cosmos db account or emulator:

`az_delete_cosmosdb_databases.sh` can be used to delete all databases in an Azure Cosmos DB account or Cosmos DB emaultor.


### Delete databases on emulator:

If you are a oh-my-zsh user, you need to invoke the script with "bash" as following (don't use oh-my-zsh directly):

```bash
bash az_delete_cosmosdb_databases.sh -e https://10.37.129.3:8081
```

This assumes emulator is accessable on "https://10.37.129.3:8081". If you have emulator reachable on different IP pass that here.

### Delete databases in Azure Cosmos DB cloud:

make sure you have logged in with azure-cli, otherwise run the following command:
```bash
az login
```

to delete all the databases within your azure cosmosdb account, run the following command:

```bash
bash az_delete_cosmosdb_databases.sh -s YOUR_SUB_NAME -g YOUR_RESOURCE_GROUP -n YOUR_COSMOSDB_ACCOUNT_NAME 
```
