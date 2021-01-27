# Self Hosted Runner Example

## Add a runner

Settings - Actions - Self Hosted Runners

Select your OS version and architecture

## Download

Configure the runner under the \actions-runner directory

```
# Create a folder under the drive root
$ mkdir actions-runner; cd actions-runner# Download the latest runner package
$ Invoke-WebRequest -Uri https://github.com/actions/runner/releases/download/v2.276.1/actions-runner-win-x64-2.276.1.zip -OutFile actions-runner-win-x64-2.276.1.zip# Extract the installer
$ Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$PWD/actions-runner-win-x64-2.276.1.zip", "$PWD")
```

## Configure

```
# Create the runner and start the configuration experience
$ ./config.cmd --url https://github.com/chessbuzz/selfhosted-runner-example --token ############### # Run it!
$ ./run.cmd
```

## Using your runner in your workflow
```
runs-on: self-hosted
```
