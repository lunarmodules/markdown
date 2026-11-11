# Releases

## Overview

This document provides guidance to publish a new release for `markdown`.

## Steps before pushing a new tag

1. Create a feature branch for the changes;

2. Bump the version on `MARKDOWN_VERSION` variable defined in the file `markdown.lua`;

> [!IMPORTANT]
>
> The version assigned to `MARKDOWN_VERSION` must match the upcoming tag and also the following regex pattern: `^[0-9]+(\.[0-9]+)+$`. Thus, `0.35.1` is allowed, `0.35` is also allowed, but a single number `1` is **NOT** allowed (*unless this pattern is fixed on every spot at [./.github/workflows/publish.yml](./.github/workflows/publish.yml)*).

3. Based on the development rockspec, create a new release rockspec inside the directory `rockspecs` (e.g.: `rockspecs/markdown-0.35-1.rockspec`) changing both the rockspec name and the field `local package_version`;

4. Make sure the created rockspec (**CHANGE** `rockspecs/markdown-0.35-1.rockspec` below to the new name) prints the expected output running the following script from the terminal or command line:

    ```bash
    lua -e "dofile(arg[0]); print(); print('package  :', package); print('version  :', version); print('branch   :', source.branch); print('tag      :', source.tag); print('url      :', source.url); print('homepage :', description.homepage); print();" -- rockspecs/markdown-0.35-1.rockspec
    ```

5. Make sure `luarocks make` is able to build the project correctly for the fresh rockspec;

6. Create entries in the changelog describing the changes for the new version:

    * in the file [CHANGELOG.md](./CHANGELOG.md);
    * in the top of the file `markdown.lua`;

7. Commit the changes and push them to the remote repository;

## Tagging a new release

After all the previous steps were performed:

1. Create a new annotated tag (e.g.: `git tag -a "0.35" -m "Release 0.35"`) changing `0.35` in the previous command to contain the exact **SAME VERSION** on `MARKDOWN_VERSION` variable defined in the file `markdown.lua`;

2. Push the new tag to the remote repository (e.g.: `git push origin 0.35`);

## Publish to LuaRocks and GitHub Releases

Once a new tag was released, select the `Publish` action on GitHub Web to trigger it manually:

1. In the UI, select the latest tag pushed in the previous step;
2. Hit the button to run the `Publish` action using the chosen tag.

> [!TIP]
>
> In order to account for intermittent failures (e.g.: connection issues, unavailable services) during the process to publish `markdown` to either LuaRocks or GitHub Releases, two input fields were added to skip the upload to each service in separate.
>
>   * `skip-luarocks-upload` (default: `false`): on GitHub Web UI, when the checkbox is ticked (this value is set to `true`), the `publish.yml` workflow does **NOT** upload to LuaRocks.org website.
>
>   * `skip-github-release` (default: `false`): on GitHub Web UI, when the checkbox is ticked (this value is set to `true`), the `publish.yml` workflow does **NOT** publish to GitHub Releases
