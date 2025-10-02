# Using Kind

## Installation (Windows)
1. Install Podman Desktop from [here](https://podman-desktop.io/).
2. Install Kind by following the instructions [here](https://kind.sigs.k8s.io/docs/user/quick-start/#installation).
    2.1 Download the Kind binary:
    ```pwsh
    curl.exe -Lo kind-windows-amd64.exe https://kind.sigs.k8s.io/dl/v0.30.0/kind-windows-amd64
    ```


    2.2 Move the binary to a directory of your choice:
    ```pwsh
        Move-Item .\kind-windows-amd64.exe c:\some-dir-in-your-PATH\kind.exe
    ```

    2.3 Add that directory to your PATH environment variable if it's not already there.

    2.4 Verify the installation:
    ```pwsh
    kind --version
    ```

3. (Optional) Kind auto-detects if you are using Docker, Podman or Nerdctl. These are experimentally supported, so if you want to explicitly set the container runtime, you can set the `KIND_EXPERIMENTAL_PROVIDER` environment variable to either `podman`, `docker`, or `nerdctl`.
    For example, to set it to Podman in PowerShell:
    ```pwsh
    $env:KIND_EXPERIMENTAL_PROVIDER="podman"
    ```
    or in Command Prompt:
    ```cmd
    set KIND_EXPERIMENTAL_PROVIDER "podman"
    ```

4. Create a Kind cluster:
    ```pwsh
    kind create cluster --name my-cluster
    ```

5. Verify the cluster is running:
    ```pwsh
    kubectl cluster-info --context kind-my-cluster
    ```

6. To delete the cluster when you're done:
    ```pwsh
    kind delete cluster --name my-cluster
    ```

