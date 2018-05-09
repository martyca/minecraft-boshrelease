# BOSH-deployed minecraft Server

This [BOSH](https://bosh.io/) release deploys a minecraft server, this release is mostly for entertainment and eductational purposes.

### 0. Quick Start

#### 0.0 Quick Start: Pre-requisites

You must have a BOSH Director and have uploaded stemcells to it. Our examples assume the [BOSH CLI v2](https://github.com/cloudfoundry/bosh-cli).

Follow the instructions to install BOSH Lite: <https://bosh.io/docs/bosh-lite>;
upload the Cloud Config.

Upload Ubuntu stemcell

```bash
bosh -e vbox us https://s3.amazonaws.com/bosh-core-stemcells/warden/bosh-stemcell-3468-warden-boshlite-ubuntu-trusty-go_agent.tgz
```

Clone the minecraft repository:

```bash
cd ~/workspace
git clone https://github.com/martyca/minecraft-boshrelease.git
cd minecraft-boshrelease
```

#### 0.1 Quick Start: Upload release to BOSH Director

```bash
git clone https://github.com/martyca/minecraft-boshrelease.git
cd minecraft-boshrelease
bosh -e vbox upload-release
```

#### 0.2 Quick Start: deploy

(This assumes you're in the `~/workspace/minecraft-boshrelease` directory cloned in a previous step):

```bash
bosh -e vbox -d minecraft deploy manifests/minecraft-lite.yml
```
#### 0.3 Quick Start: test

list running vm's
```
bosh -e vbox -d minecraft vms
```

Start your minecraft client
select multiplayer, direct connection.
copy ip of vm.
