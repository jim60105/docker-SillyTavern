# docker-SillyTavern

This is the docker image for [SillyTavern: LLM Frontend for Power Users.](https://github.com/SillyTavern/SillyTavern) from the community.

Get the Dockerfile at [GitHub](https://github.com/jim60105/docker-SillyTavern), or pull the image from [ghcr.io](https://ghcr.io/jim60105/sillytavern) or [quay.io](https://quay.io/repository/jim60105/sillytavern?tab=tags).

## Usage Command

First, set the default password for the `default-user` account by the following command.  
Replace `SHOULD_CHANGE_THIS_PASSWORD` with your desired password.

```bash
docker compose run --rm sillytavern_recover default-user SHOULD_CHANGE_THIS_PASSWORD
```

Then, start the container.

```bash
docker compose up -d
```

The default port is `8000`. You can access the web interface by visiting `http://localhost:8000`.

### Build Command

> [!IMPORTANT]  
> Clone the Git repository recursively to include submodules:  
> `git clone --recursive https://github.com/jim60105/docker-SillyTavern.git`

```bash
docker build -t SillyTavern .
```

> [!NOTE]  
> If you are using an earlier version of the docker client, it is necessary to [enable the BuildKit mode](https://docs.docker.com/build/buildkit/#getting-started) when building the image. This is because I used the `COPY --link` feature which enhances the build performance and was introduced in Buildx v0.8.  
> With the Docker Engine 23.0 and Docker Desktop 4.19, Buildx has become the default build client. So you won't have to worry about this when using the latest version.

## LICENSE

> [!NOTE]  
> The main program, [SillyTavern](https://github.com/SillyTavern/SillyTavern), is distributed under [AGPL-3.0 license](https://github.com/SillyTavern/SillyTavern/blob/release/LICENSE).  
> Please consult their repository for access to the source code and licenses.  
> The following is the license for the Dockerfiles and CI workflows in this repository.

<img src="https://github.com/user-attachments/assets/268109a2-7194-491c-9020-3d53860f3fe3" alt="agplv3" width="300" />

[GNU AFFERO GENERAL PUBLIC LICENSE Version 3](/LICENSE)

This program is free software: you can redistribute it and/or modify it under the terms of the GNU Affero General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License along with this program. If not, see <https://www.gnu.org/licenses/>.

> [!CAUTION]  
> An AGPLv3 licensed Dockerfile means that you ***MUST*** **distribute the source code with the same license**, if you
>
> - Re-distribute the image. (You can simply point to this GitHub repository if you doesn't made any code changes.)
> - Distribute a image that uses code from this repository.
> - Or **distribute a image based on this image**. (`FROM ghcr.io/jim60105/sillytavern` in your Dockerfile)
>
> "Distribute" means to make the image available for other people to download, usually by pushing it to a public registry. If you are solely using it for your personal purposes, this has no impact on you.
>
> Please consult the [LICENSE](LICENSE) for more details.

[![CodeFactor](https://www.codefactor.io/repository/github/jim60105/docker-SillyTavern/badge)](https://www.codefactor.io/repository/github/jim60105/docker-SillyTavern) [![GitHub Workflow Status (with event)](https://img.shields.io/github/actions/workflow/status/jim60105/docker-SillyTavern/scan.yml?label=IMAGE%20SCAN)](https://github.com/jim60105/docker-SillyTavern/actions/workflows/scan.yml)
