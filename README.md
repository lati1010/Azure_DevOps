This Pipeline will help in uploading maps in Azure Integration account from Azure REPO and stores the file temporarily on Azure blob and deletes once pipeline is finished

We have added new Task in script specially for Liquid file as Azure blob stores the Files and changes the Content-type as application/octet-stream instead of text/plain.

Please add the Static secrects and sensitive information into Azure key vault and link the key vault to Azure DevOps-->Library-->Variables-->Group-->link keyvault secrets 

Variables mentioned below has to be passed as input variables every time we trigger the pipeline. Add as Pipeline variables and check the box to Let users override this value when running this pipeline.

      blob_name = "$(blob_name)"
      map_name = "$(map_name)"
      map_type = "$(map_type)"
      contentType = "$(contentType)"
      repo_path = "$(repo_path)"
