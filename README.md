## memo
起動に10分かかる

## command

```
az upgrade
az bicep install

az login

 az account list \
   --refresh \
   --query "[].id" \
   --output table

az account set --subscription 208f0e61-8983-46ba-916c-cb0412aae9aa

group_name=20211027HappyHackLineBot

az group create --name ${group_name} --location japaneast

az configure --defaults group=${group_name}

## https://1password.com/jp/password-generator/
az deployment group create --name deployPrj01 --template-file main.bicep \
  --parameters ramdom=iJtqJ9qgxgzXw2e88RNP \
  --parameters secret=0db4791853e3fd582de47d536f4282b7\ \
  --parameters access=aVPxyQC8gp8H17nOgJxgjhOlQT5Wg6xSeUjfMpC6Jf4HtEaSpgCpON/ZWhg18LwZEZPZuYukcJJ97UUUxH1/lAOPPjwwKCUHVMlyTgKxw3OtlPFwdAAUm2oDEuB1mrM7EU4zf9ttLYsNBSQFzn56JwdB04t89/1O/w1cDnyilFU=
  
az deployment group show \
  -g ${group_name} \
  -n deployPrj01 \
  --query properties.outputs.functionAppName.value

cd deployPrj01
npm i
func azure functionapp publish fn-ijtqj9qgxgzxw2e88rnp --build remote

https://fn-ijtqj9qgxgzxw2e88rnp.azurewebsites.net/api/linehttptriggeredfunction


2回目以降
az login
cd deployPrj01
func azure functionapp publish fn-ijtqj9qgxgzxw2e88rnp --build remote
https://fn-ijtqj9qgxgzxw2e88rnp.azurewebsites.net/api/linehttptriggeredfunction







#az group delete --name ${group_name}
```

##

https://azure.github.io/AppService/2021/07/23/Quickstart-Intro-to-Bicep-with-Web-App-plus-DB.html
