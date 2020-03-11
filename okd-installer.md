## OKD install on GCP
### Screenshot tour

Vadim Rutkovsky

vrutkovs@redhat.com

---

### Goals

* Install OKD 4.4 on GCP via IPI flow
* Show known issues

---
### Install config template
![config](imgs/img00.png)

---
### Custom wrapper around installer

![make-gcp](imgs/img01.png)

https://github.com/vrutkovs/okd-installer

---
### Pull latest installer image

![make-gcp](imgs/img02.png)

---
### Check version and release image

![version](imgs/img03.png)

---
### Template install-config

![template](imgs/img04.png)

---
### Run `create cluster` from container

![run](imgs/img05.png)

---
### Store cluster output in `clusters/<name>`

![run](imgs/img05_1.png)

---
### Mount GCP credentials

![run](imgs/img05_2.png)

---
### Start cluster install

![run](imgs/img05_3.png)

---
### Override FCOS image location and release image

![run](imgs/img05_4.png)

---
### Installer output

![output](imgs/img06.png)

---
### GCP masters created

![masters](imgs/img07.png)

---
### Bootstrap node

![bootstrap](imgs/img08.png)

---
### Bootkube: pivot

![pivot](imgs/img09.png)

---
### Bootkube: updated bootstrap

![pivoted-instance](imgs/img10.png)

---
### Bootkube: watch install progress

![install-progress](imgs/img11.png)

---
### Bootkube: network

![network](imgs/img12.png)

---
### Bootkube: masters are ready

![masters-ready](imgs/img13.png)

---
### machine-api for workers

![machinesets](imgs/img14.png)

---
### Workers on GCP console

![gcp-workers](imgs/img15.png)

---
### Workers joining the cluster

![worker-join](imgs/img16.png)

---
### Operators doing the needful

![operators](imgs/img17.png)

---
### tada.wav

![done](imgs/img18.png)

---
### Authentication files

![auth](imgs/img19.png)

---
### Known issues with GCP

* FCOS is not yet officially uploaded

  Workaround: upload `tar.gz` manually and use
  
  `OPENSHIFT_INSTALL_OS_IMAGE_OVERRIDE="
  https://storage.googleapis.com/..."`

* "Waiting up to 40m0s for bootstrapping to complete" never completes, although cluster is setup
  
  Destroy bootstrap node manually

---
## Questions?

https://vrutkovs.github.io/slides-okd-installer-screenshots
