***Upload_Maps_to_Azure_IntegrationAccount.yml***

This Pipeline will help in uploading maps in Azure Integration account from Azure REPO and stores the file temporarily on Azure blob and deletes once pipeline is finished

We have added new Task in script specially for Liquid file as Azure blob stores the Files and changes the Content-type as application/octet-stream instead of text/plain.

Please add the Static secrects and sensitive information into Azure key vault and link the key vault to Azure DevOps-->Library-->Variables-->Group-->link keyvault secrets 

Variables mentioned below has to be passed as input variables every time we trigger the pipeline. Add as Pipeline variables and check the box to Let users override this value when running this pipeline.

      blob_name = "$(blob_name)"
      map_name = "$(map_name)"
      map_type = "$(map_type)"
      contentType = "$(contentType)"
      repo_path = "$(repo_path)"

***Resubmit_Azure_LogicApp_using_Workflow_RunID.yml***

This pipeline will help in resubmitting the failed/success workflow based on the previous RunID.

This will first validate if the RUNID is present in the specified Azure subscription and then resubmits the LogicApp workflow from its previous RUNID.

Variables mentioned below has to be passed as input variables every time we trigger the pipeline. Add as Pipeline variables and check the box to Let users override this value when running this pipeline.

$(Logicapp_Name)
$(Logicapp_run_Identifier)
$(subscriptionID)
$(Resourcegroup_name)
$(SubscriptionName)
