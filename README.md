- 👋 Hi, I’m @MalesForFemalesLLC22
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
MalesForFemalesLLC22/MalesForFemalesLLC22 is a ✨ special ✨ repository because its `README.md` (https://github.com/Madib036/MMFLLC/blob/main/.github%2Fdependabot.yml) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->(https://malesforfemalesllc.atlassian.net/gateway/api/compass/v1/webhooks/4283432c-68d4-41d9-afa0-180b198c35eb)
''name: Auto Assign
on:
  issues:
    types: [opened]
  pull_request:
    types: [opened]
jobs:
  run:
    runs-on: ubuntu-latest
    permissions:
      issues: write
      pull-requests: write
    steps:
    - name: 'Auto-assign issue'
      uses: pozil/auto-assign-issue@v1
      with:
          repo-token: ${{ secrets.GITHUB_TOKEN }}
          assignees: Madib036
          numOfAssignee: 1''