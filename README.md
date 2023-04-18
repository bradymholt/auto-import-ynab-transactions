This repository contains a GitHub Action workflows that will automatically import YNAB transactions from linked bank accounts on a recurring basis by utilizing the [YNAB API](https://api.ynab.com/).

You can fork this repository and use it to import transactions on your own YNAB account.

## Setup

1. Create a new YNAB API personal access token by following the instructions [here](https://api.ynab.com/#personal-access-tokens).
1. Fork this repository
1. In the forked repo, go to Settings > Secrets and variables > Actions, and create a new repository secret named `YNAB_API_ACCESS_TOKEN` with the value of the API token you created in step 1.

    ![Create GitHub Actions secret](https://user-images.githubusercontent.com/759811/232794388-9781419c-596c-4285-bad5-89b07e487567.png)


    You can optionally add another secret named `YNAB_BUDGET_ID` with the value of your YNAB budget ID for which you want to import transctions on. If you don't specify this secret, the "last used" budget will be targeted.

By default the workflow will run automatically every 6 hours but you can change it by modifying the cron schedule in the `.github/workflows/import-ynab-transactions.yml` file.