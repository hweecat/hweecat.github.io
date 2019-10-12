---
layout: post
title: "TIL: Migrating Git repositories manually from GitLab to Azure DevOps (TFS)"
description: "Quick migration guide from GitLab to Azure DevOps (TFS) - adapted from migration guide prepared for my development team"
excerpt: "My development team has been using GitLab on-premise to manage their code repositories. As we are moving development work to our new on-premise development cloud with expanded processing capabilities, we also need to migrate our code repositories to the new development cloud which uses Azure DevOps Team Foundation Server (TFS) for Git workflows. To support the chief architect in the migration, I prepared a quick migration guide for the team's move to Azure DevOps TFS."
---
---

## Background

My development team has been using GitLab on-premise to manage their code repositories. As we are moving development work to our new on-premise development cloud with expanded processing capabilities, we also need to migrate our code repositories to the new development cloud which uses Azure DevOps Team Foundation Server (TFS) for Git workflows. To support the chief architect in the migration, I prepared a quick migration guide for the team's move to Azure DevOps TFS.

Our existing and new on-premise development clouds are accessible via different Virtual Private Networks (VPN), hence we had to migrate our code repositories manually instead of using the automatic Git migrator in Azure DevOps TFS. If your code repository services are within the same network, automatic migration is possible.

### Creating local Git repository from GitLab

1. Log into existing cloud VPN (if applicable).

2. Open Git Bash.

3. Navigate into target local directory.

4. Clone your GitLab source repository (e.g. YourTeam/YourSourceRepo) to target local directory.

```bash
git clone http://myteamgitlabaddress/YourTeam/YourSourceRepo
```

### Creating new upstream at Azure DevOps (TFS)

1. Log into new cloud VPN (if applicable).

2. Create target repository at Azure DevOps. (e.g. YourTargetRepo)

3. Open Git Bash.

4. List the current configured remote repository for your (GitLab) fork.

```bash
git remote -v
```

5. Specify a new remote upstream repository that will be synced with the fork.

```bash
git remote add upstream http://myteamtfsaddress:8080/tfs/DefaultCollection/_git/YourTargetRepo
```

6. Verify the new upstream repository you've specified for your fork.

```bash
git remote -v
```

### Migrating codes from GitLab to Azure DevOps (TFS)

1. Log into existing cloud VPN (if applicable).

2. Check that local repository is up to date with GitLab upstream. 

```bash
git fetch
```

3. Update local repository with GitLab repository.

```bash
git pull
```

4. Connect to new cloud VPN (if applicable).

5. Push local repository to Azure DevOps (TFS).

```bash
git push --mirror http://myteamtfsaddress:8080/tfs/DefaultCollection/_git/YourTargetRepo
```

    - You need to key in your Azure DevOps (TFS) username and password for authentication.
    - If authentication error, try

    ```bash
    git config --system --unset credential.helper
    ```
    
    to clear cache.

