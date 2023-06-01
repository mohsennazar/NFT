# NFT
TALKI
name: Mark stale pull requests

on:
  schedule:
  - cron: "0 */6 * * *"

jobs:
  stale:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/stale@v3
      with:
        repo-token: ${{ secrets.GITHUB_TOKEN }}
        days-before-pr-stale: 14
        days-before-pr-close: 90
        stale-pr-label: inactive
        close-pr-label: auto-close
        exempt-pr-labels: keep-open
        operations-per-run: 1300
        ascending: false
        # start-date: '2021-03-19'
        stale-pr-message: >
          This pull request has been inactive for at least 14 days.
          If you are finished with your changes, don't forget to sign off. See the [contributor guide](https://review.learn.microsoft.com/help/contribute/contribute-how-to-write-pull-request-automation?branch=main) for instructions.
                    
          [Get Help](https://review.learn.microsoft.com/help/contribute/help-options?branch=main)  
          
          [Docs Support Teams Channel](https://teams.microsoft.com/l/channel/19%3a7ecffca1166a4a3986fed528cf0870ee%40thread.skype/General?groupId=de9ddba4-2574-4830-87ed-41668c07a1ca&tenantId=72f988bf-86f1-41af-91ab-2d7cd011db47)  
          
          [Resolve Merge Conflict](https://review.learn.microsoft.com/help/contribute/resolve-merge-conflicts?branch=main)  
        
