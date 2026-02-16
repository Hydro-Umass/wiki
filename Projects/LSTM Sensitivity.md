This is the main page for the LSTM Sensitivy project.


# Setting up environment

1. Install cachix in bash:
`nix-env -iA cachix -f https://cachix.org/api/v1/install`

Use the devenv cache to speed up installation
`cachix use devenv`

2. Install devenv in bash:
`nix profile install --accept-flake-config github:cachix/devenv/latest`

3. Enable Nix Flakes (if not already enabled) in bash:
`mkdir -p ~/.config/nix
echo "experimental-features = nix-command flakes" >> ~/.config/nix/nix.conf`

Check if nix is updated and flakes are enabled:
`nix upgrade-nix
nix-env --version`

4.  Create First devenv Project
`mkdir my-project && cd my-project`

Initialize devenv
`devenv init`

Edit devenv.nix to add what you need
`nano devenv.nix`

Enter the development shell
`devenv shell`

## Start working with developed devenv environment

1. Navigate to your project directory
`cd /path/to/my/project`

2. Enter the environment
`devenv shell`

3.  When done, exit
`exit`


Here is Quick Command Reference:

Enter environment: `devenv shell`

Start services (databases, etc.): `devenv up`

Run tests: `devenv test`

Update dependencies: `devenv update`

Search for packages: `devenv search <name>`




