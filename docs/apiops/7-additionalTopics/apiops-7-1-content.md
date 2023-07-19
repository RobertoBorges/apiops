---
title: Repo Contents
parent: Additional Topics
has_children: false
nav_order: 1
---


| Path | Purpose |
| - | - |
| tools/azdo_pipelines/| azure devops pipelines for running the extractor and publisher tools
| tools/.github/workflows/ | Github actions for running the extractor and publisher tools |
| tools/code | Source code for the extractor and publisher tools |
| tools/utils/create_pull_request.sh | Script to allow the Azure Devops extractor pipeline to create a Git Pull Request. Not required if using Github actions |
| configuration.extractor.yaml | A sample yaml extractor configuration file to signal to the extractor to extract select apis, backends, products, tags, loggers,and namedvalues. This is an optional parameter and will only come into play if you want different teams to manage different apis, tags, etc.. You typically will have one configuration per team. Note: You can call the file whatever you want as long as you reference the right file within your extractor pipeline. On a side note since the introduction of Workspaces we believe they are the better solution compared to using this file, but we are keeping the support as not everyone will be able to use workspaces. |
| configuration.[env].yaml | A sample yaml publisher configuration file to override configuration when running the publisher to promote across different environments (e.g. configuration.prod.yaml for prod environment). Although its optional parameter, you are expected to provide a unique file for each environment as usually different environments have different values (e.g. namevalue). For example if you have a QA environment you would provide another file called configuration.qa.yaml which would have qa specific configuration. Note: You can call the file whatever you want as long as you reference the right file within your publisher pipeline. Also note that if you don't pass the target instance name in the pipelines themselves then you have to pass it as part of the configuration file itself |
| sample-artifacts-folder | Sample output from the extractor tool. The publisher tool expects this structure and can automatically push changes back to Azure |