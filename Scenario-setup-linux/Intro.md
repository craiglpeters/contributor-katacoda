TO DOs
 - [ ] Verify desired name
 - [ ] Rename repo
 - [ ] Edit copy and break into step md files
 - [ ] Fix index.json

# Welcome to the kubernetes contributior playground in Codespaces!
In this scenario we will become familiar with the a cloud based tool where we'll run and test Kubernetes called [GitHub Codespaces](https://docs.github.com/en/codespaces). Codespaces is a service hosted on GitHub that takes care of creating a running development environment, cloning (and optionally forking) the GitHub repository, runs  configured setup and configuration, manages secrets, saves your work between sessions, and more. In this repository Codespaces is configured to take care of (ALL?) of the configuration that the steps in the running locally section below describe. Additionally you can [personalize](https://docs.github.com/en/codespaces/customizing-your-codespace/personalizing-github-codespaces-for-your-account) your Codespaces experience so you have just the VS Code extensions, themes, and dotfiles you love.

- Step 1: You don't need to worry about forking the project. Codespaces will make a fork for you when you make a commit because the main branch is protected (TO DO verify branch protection)
- Step 2: Go and package-essential are already installed on the Codespaces environment (part of the [default "universal" Linux container image](https://github.com/devcontainers/images/tree/main/src/universal)). Verify this by running the command `go version` in the terminal (normally below unless you've changed your VS Code layout). (TO DO: verify that the correct version of go is available - as of 2022-09-14 `go version go1.19` linux/amd64 is in the universal image - an update can be made to the devcontainer.json to specify a different version)
- Step 3: (git clone is done automatically in Codespaces)
The 4-core machine has, at the start
```
$ free -h
              total        used        free      shared  buff/cache   available
Mem:          7.8Gi       1.5Gi       184Mi       0.0Ki       6.1Gi       6.0Gi
Swap:            0B          0B          0B

$ df -h
Filesystem      Size  Used Avail Use% Mounted on
overlay          32G   13G   18G  42% /
tmpfs            64M     0   64M   0% /dev
tmpfs           3.9G     0  3.9G   0% /sys/fs/cgroup
shm              64M  8.0K   64M   1% /dev/shm
/dev/sdb1        29G   11G   19G  36% /usr/sbin/docker-init
/dev/loop0       32G   13G   18G  42% /workspaces
/dev/sda1        32G  272K   30G   1% /tmp
```

(TO DO verify if these are suffient resources) which may not be sufficient. Will move to an 8-core machine if required.
- Step 4: (obsolete in Codespaces)
- Step 5: Run `make test` in the terminal
- Step 6: seems redundant with Step 5

## Running Locally (TO DO: this is currently the old content - need to clean it up given new context)
In this scenario, we'll work through the steps to set up Kubernetes in a Linux-based environment (here Ubuntu), that you might require to contribute to the project. Using this environment, we will also run some common tests to help you understand how the CI runs these tests when you open up a PR, and how you can run them in your environment as well!

More details can be found on [Kubernetes Contributors Guide](https://github.com/kubernetes/community/blob/master/contributors/guide/README.md).

Let's jump in! 🤓