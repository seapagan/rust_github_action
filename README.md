# Create Rust binaries in a GitHub Release

This is an example github action that will create linux/windows/macOS binaries
for a Rust Project, automatically when a new release is created (or even a new
tag).

The binaries are uploaded to the release/tag as assets.

> [!TIP]
>
> The rust project in this example is a simple hello world, just to enable
> testing of the action. All you need is the action file
> `.github/workflows/release.yml`

## Setup

You need to enable `Read and Write` permissions for the `actions` user in your
repository. This is needed to upload the binaries to the release. This is done
in the `Settings` -> `Actions` -> `General` -> `Workflow permissions` section.

> [!NOTE]
>
> This is the **REPOSITORY** settings, not your global user or organization
> settings.

## Usage

Upload `.github/workflows/release.yml` to your repository in the same path, and
change the `$BINARY_NAME` to the name of your binary (generally the name of the
project in the `Cargo.toml`).

Now, create a NEW Release or Tag, the action will run and automatically create
binaries for `Linux` (standard Glibc and musl), `Windows`, and `MacOS` (x86_64
and aarch64).

## Plans

Will probably add linux targets for `aarch64` and `armv7` in the future too. I
had this working but needs some more testing and a refactor.
