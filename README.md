# Cortex Code Control Hub

The [Enterprise CoCo (Cortex Code) Governance on Snowflake](https://www.snowflake.com/en/developers/guides/cortex-code-control-hub/) quickstart walks us through the deployment of CoCo Control Hub.

The code is managed in Snowflake's [sfquickstarts](https://github.com/Snowflake-Labs/sfquickstarts.git) GitHub repository, which is 11 GB in size.

This repository contains the truncated version of that repository with onlye the code for the cortex-code-control-hub application.

## Truncate Repository

```bash
# clone original repo
git clone https://github.com/Snowflake-Labs/sfquickstarts.git
cd sfquickstarts

# keep some of the global files
tar -cvf /tmp/sfquickstarts_cortex-code-control-hub.tar \
  LICENSE SECURITY.md .gitignore

# remove everything other than cortex-code-control-hub, incl. history
git filter-repo --path site/sfguides/src/cortex-code-control-hub
git filter-repo --subdirectory-filter site/sfguides/src/cortex-code-control-hub

# restore global files
tar -xvf /tmp/sfquickstarts_cortex-code-control-hub.tar
git add .
git commit -m 'LICENCE and other generic files from the original repository'

# push to new empty repo
git remote add origin https://github.com/lziegler/cortex-code-control-hub.git
git branch -M main
git push -u origin main
```
