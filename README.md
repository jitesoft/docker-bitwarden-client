# Bitwarden Client

Bitwarden-cli client built from source for Alpine linux and Distroless.

Bitwarden is an open source password manager which can be used both with a SaaS License or by
self hosting.  
The CLI client can be used in CI/CD or by anyone who prefer to not use a Desktop or Web based password manager client.

### Usage

Authentication can easily be done by using an API key created in the bitwarden web client, 
the CLI client uses the `BW_CLIENTID` and `BW_CLIENTSECRET` environment variables which can be used
when in a non-interactive mode.

The image exposes the `AUTO_LOGIN` and `AUTO_UNLOCK` env variables, allowing you to automatically login and unlock vault on
startup (via the entrypoint script).

```shell
docker run --rm -i -t -e BW_CLIENTID=abc123 -e BW_CLIENTSECRET=abc123 -e AUTO_LOGIN=true -e AUTO_UNLOCK=true jitesoft/bitwarden-client bw ...
# Alt
docker run --rm -i -t -e BW_CLIENTID=abc123 -e BW_CLIENTSECRET=abc123 -e jitesoft/bitwarden-client /bin/ash
 > bw login
 > bw unlock
 > bw ...
```

### Dockerfile

Dockerfile and scripts can be found at [GitLab](https://gitlab.com/jitesoft/dockerfiles/bitwarden-client) or [GitHub](https://github.com/jitesoft/docker-bitwarden-client).

### Image labels

This image follows the [Jitesoft image label specification 1.0.0](https://gitlab.com/snippets/1866155).

### Signature

Cosign public key for this image can be found at [https://jitesoft.com/cosign.pub](https://jitesoft.com/cosign.pub).

### Licenses

This repository is released under the [MIT license](LICENSE).  
Bitwarden cli source code is released under the [GNU General Public License v3.0](https://github.com/bitwarden/cli/blob/master/LICENSE.txt).  

Check [dependency graph](https://github.com/bitwarden/cli/network/dependencies) for full dependencies and licensing of the bitwarden cli project.

### Sponsors

Jitesoft images are built via GitLab CI on runners hosted by the following wonderful organisations:

<a href="https://fosshost.org/">
  <img src="https://raw.githubusercontent.com/jitesoft/misc/master/sponsors/fosshost.png" height="128" alt="Fosshost logo" />
</a>
<a href="https://www.aarch64.com/">
  <img src="https://raw.githubusercontent.com/jitesoft/misc/master/sponsors/aarch64.png" height="128" alt="Aarch64 logo" />
</a>

_The companies above are not affiliated with Jitesoft or any Jitesoft Projects directly._

---

Sponsoring is vital for the further development and maintaining of open source.  
Questions and sponsoring queries can be made by <a href="mailto:sponsor@jitesoft.com">email</a>.  
If you wish to sponsor our projects, reach out to the email above or visit any of the following sites:

[Open Collective](https://opencollective.com/jitesoft-open-source)  
[GitHub Sponsors](https://github.com/sponsors/jitesoft)  
[Patreon](https://www.patreon.com/jitesoft)
