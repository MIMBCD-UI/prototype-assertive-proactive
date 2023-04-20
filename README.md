# Assertive and Proactive Prototype 

<img src="https://github.com/MIMBCD-UI/prototype-multi-modality/blob/master/assets/banner.png?raw=true"/>

[![OpenCollective](https://opencollective.com/oppr/backers/badge.svg?style=flat-square)](#backers)
[![OpenCollective](https://opencollective.com/oppr/sponsors/badge.svg?style=flat-square)](#sponsors)
[![Gitter](https://img.shields.io/gitter/room/gitterHQ/gitter.svg?style=flat-square)](https://gitter.im/opprTeam)
[![Twitter](https://flat.badgen.net/badge/icon/twitter?icon=twitter&label)](https://twitter.com/opprGroup)

Welcome to the results repository for our paper "[*Assertiveness-based Agent Communication for a Personalized Medicine on Medical Imaging Diagnosis*](https://doi.org/10.1145/3544548.3580682)" ([10.1145/3544548.3580682](https://doi.org/10.1145/3544548.3580682)) in [proceedings of the 2023 CHI Conference on Human Factors in Computing Systems](https://dl.acm.org/doi/proceedings/10.1145/3544548) ([CHI '23](https://chi2023.acm.org/)) presented during the "[AI in Health](https://programs.sigchi.org/chi/2023/program/session/97368)" track. In this repository, we aim to develop a prototype of the assertive and proactive trial for the [Assertiveness-based BreastScreening-AI](https://doi.org/10.1145/3544548.3580682) condition. The prototype is based on an early developed version of the [BreastScreening](https://github.com/MIMBCD-UI/prototype-breast-screening) prototype. To test and validate the prototype, initial [User Research](https://github.com/mida-project/meta/wiki/User-Research) studies with the prototype are [linked](https://github.com/MIMBCD-UI/meta/wiki/User-Research#test-11-assertiveness-based-assistant-pre-master-thesis-of-jo%C3%A3o-fernandes-) ([10.13140/RG.2.2.22989.92645/1](http://dx.doi.org/10.13140/RG.2.2.22989.92645/1)). A number of advantages over the introduction of our novel proposed type of interactive techniques appear to be evident. Furthermore, we develop the prototype the [MIDA](https://mida-project.github.io/) project as well. The [MIDA](https://mida-project.github.io/) project is a research project that deals with the use of a recently proposed technique in literature: [Deep Convolutional Neural Networks (CNNs)](https://en.wikipedia.org/wiki/Convolutional_neural_network). These deep networks will incorporate information from several different modes by a User Interface (UI) implemented based on our later [prototypes](https://github.com/mida-project/meta/wiki/Prototypes). We also have several [channels](https://github.com/MIMBCD-UI/meta/wiki/Channels) and demos to see in our [YouTube Channel](https://www.youtube.com/channel/UCPz4aTIVHekHXTxHTUOLmXw), please follow us!

<a href="https://www.patreon.com/oppr" target="_blank">
<img src="https://c5.patreon.com/external/logo/become_a_patron_button@2x.png" width="160">
</a>

## Instructions

First of all, you will need [NodeJS](https://nodejs.org/) installed locally on your machine. This project needs both [`npm`](https://www.npmjs.com/) and [`http-server`](https://github.com/indexzero/http-server) dependencies to install and run the core project. If you do not have those installed please follow the [`INSTALL`](src/INSTALL.md) instructions.

### DICOM Server

The following assumes you will be using a [git](https://git-scm.com/) version control for this repository, storing thanks to [GitHub](https://github.com/). First, [Download](https://git-scm.com/downloads) and [Install](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) [git](https://git-scm.com/). Our system needs to be integrated with [WADO-URI](http://dicom.nema.org/dicom/2013/output/chtml/part18/sect_6.3.html) servers, [DICOMWeb](https://www.dicomstandard.org/dicomweb/) servers or any HTTP based server that returns a [DICOM P10](http://www.web3.lu/dicom-standard/) instances. We suggest you to use an [Orthanc](https://www.orthanc-server.com/) server, since it is a simple and powerful [**standalone DICOM server**](https://www.orthanc-server.com/static.php?page=about) by providing a [**RESTful API**](https://en.wikipedia.org/wiki/Representational_state_transfer).

You can [download](https://www.orthanc-server.com/download.php) a latest version or you can use our own sample of an [Orthanc](https://www.orthanc-server.com/) version with our examples of patient images. The instructions to use our solution are as follows.

#### Clone

1.1.1. Clone the DICOM Server [repository](https://github.com/MIMBCD-UI/dicom-server):

```
git clone git@github.com:MIMBCD-UI/dicom-server.git
```

1.1.2. Go inside the project folder:

```
cd dicom-server/
```

#### Install

1.2.1. Install the local dependencies:

```
npm install
```

1.2.2. You can now **Run** the project, just follow the [next section](https://github.com/MIMBCD-UI/prototype-assertive-proactive#run).

#### Run

1.3.1. Inside the project folder:

```
cd dicom-server
```

1.3.2. Start the DICOM Server (Orthanc) for [MacOS](https://www.orthanc-server.com/static.php?page=download-mac):

```
npm run start:multi
```

**OR**

```
cd ..
cd dicom-server/orthancAndPluginsOSX.stable/
./startOrthanc.command
```

**NOTE**: If you are not using [MacOS](https://www.orthanc-server.com/static.php?page=download-mac), for instance, if you are using [Windows](https://www.orthanc-server.com/download-windows.php) or [Debian](https://packages.debian.org/search?keywords=orthanc&searchon=names&exact=1&suite=all&section=all) you have a [documentation](https://www.orthanc-server.com/static.php?page=documentation) for that. Just follow the [Windows](https://www.orthanc-server.com/resources/2015-02-09-emsy-tutorial/index.html) or [Debian](https://packages.debian.org/sid/orthanc) documentations. You also have several [other options](https://www.orthanc-server.com/download.php).

1.3.3. Open the link:

```
localhost:8248
```

NOTE: If you need some help see the [Demo](https://youtu.be/tkzpT3KpY2A).

### Main Server

Our main server uses [NodeJS](https://nodejs.org/en/) and has several [dependencies](package.json). For the following steps you must have already installed both [NodeJS](https://nodejs.org/en/) and [`npm`](https://www.npmjs.com/) in your machine.

#### Clone

2.1.1. Clone the project repository:

```
git clone git@github.com:MIMBCD-UI/prototype-assertive-proactive.git
```

2.1.2. Go inside the project folder:

```
cd prototype-assertive-proactive/
```

#### Install

2.2.1. Install the local dependencies:

```
npm install
```

2.2.2. You can now **Run** the project, just follow the [next section](#run).

#### Run

2.3.1. Inside the project folder:

```
cd prototype-lesion-bbs/
```

2.3.2. If you have already run the DICOM Server on a [previous section](https://github.com/mida-project/prototype-lesion-bbs#dicom-server), please jump to the **2.3.3.** point, otherwise do:

```
npm run dicom-server
```

2.3.3. Run the code:

```
npm run build:local
```

2.3.4. Start the project:

```
npm run start:local
```

2.3.5. Open the link:

```
localhost:8286/src/public/index.html
```

##### Allow-Control-Allow-Origin

Access-Control-Allow-Origin is a [CORS (Cross-Origin Resource Sharing) header](https://www.html5rocks.com/en/tutorials/cors/). If you want to know [How does Access-Control-Allow-Origin header work?](https://stackoverflow.com/questions/10636611/how-does-access-control-allow-origin-header-work) follow the link.

###### Google Chrome

* To deal with the CORS issue it is necessary to open [Google Chrome](https://www.google.com/intl/en/chrome/browser/desktop/) with `--disable-web-security` flag on:

```
open /Applications/Google\ Chrome.app --args --disable-web-security --user-data-dir
```

* Or install the  [CORS](https://chrome.google.com/webstore/detail/allow-control-allow-origi/nlfbmbojpeacfghkpbjhddihlkkiljbi?hl=en) plugin for [Google Chrome](https://www.google.com/intl/en/chrome/browser/desktop/).

## Information

The current information will summarize the essential parts of this repository. In addition to related resources, we address all significant parts that were crucial to the present information.

### Related Repositories

The following list, represents the set of related repositories for the presented one:

- [`prototype-xai-vis`](https://github.com/MIMBCD-UI/prototype-xai-vis)

- [`prototype-scalable-interactions`](https://github.com/MIMBCD-UI/prototype-scalable-interactions)

- [`prototype-rlc`](https://github.com/mida-project/prototype-rlc)

- [`dataset-tc`](https://github.com/MIMBCD-UI/dataset-tc)

- [`dataset-uta10-dicom`](https://github.com/MIMBCD-UI/dataset-uta10-dicom)

- [`dataset-uta10-annotations`](https://github.com/MIMBCD-UI/dataset-uta10-annotations)

### Dataset Resources

For the [User Test Analysis 8 (UTA8)](https://github.com/mida-project/meta/wiki/User-Research#test-8-explainable-assistant-introduction-) of this project we generated a combination of interesting [datasets](https://www.kaggle.com/MIMBCD-UI). To publish our [datasets](https://www.kaggle.com/MIMBCD-UI) we used a well known platform called [Kaggle](https://www.kaggle.com). To access our project's [Profile Page](https://www.kaggle.com/MIMBCD-UI) just follow the [link](https://www.kaggle.com/MIMBCD-UI). We are also working on several other [User Research](https://github.com/mida-project/meta/wiki/User-Research) studies, while this repository is being an important asset to them.

## About

For more information about the [MIDA](https://mida-project.github.io/) Project just follow the [link](https://github.com/mida-project/meta). Pieces of information about details of this repository are also in a [wiki](https://github.com/mida-project/prototype-lesion-bbs/wiki). This prototype was developed using several libraries and dependencies. Despite that all libraries had their importance and supported the development, one of it was of chief importance. The [CornerstoneJS](https://cornerstonejs.org/) library and [secondary libraries](https://github.com/cornerstonejs), respectively, are supporting this prototype. We [Acknowledge](https://github.com/mida-project/prototype-lesion-bbs/blob/master/README.md#acknowledgments) all people involved in the path.

### License

Copyright © 2019 [Instituto Superior Técnico (IST)](https://tecnico.ulisboa.pt/)

The [`prototype-lesion-bbs`](https://github.com/mida-project/prototype-lesion-bbs) repository is distributed under the terms of both [Academic License](https://github.com/mida-project/prototype-lesion-bbs/blob/master/ACADEMIC.md) and [Commercial License](https://github.com/mida-project/prototype-lesion-bbs/blob/master/COMMERCIAL.md), for academic and commercial purpose, respectively. For more information regarding the [License](https://github.com/mida-project/prototype-lesion-bbs/blob/master/LICENSE.md) of the hereby repository, just follow both [ACADEMIC](https://github.com/mida-project/prototype-lesion-bbs/blob/master/ACADEMIC.md) and [COMMERCIAL](https://github.com/mida-project/prototype-lesion-bbs/blob/master/COMMERCIAL.md) files.

### Acknowledgments

A special thanks to [Chris Hafey](https://www.linkedin.com/in/chafey/), the propelling person of [CornerstoneJS](https://cornerstonejs.org/), who also developed the [cornerstoneDemo](https://github.com/chafey/cornerstoneDemo). Not forgetting the three supporters of the CornerstoneJS library, [Aloïs Dreyfus](https://www.linkedin.com/in/alois-dreyfus), [Danny Brown](http://dannyrb.com/) and [Erik Ziegler](https://www.npmjs.com/~swederik). We also would like to give a special thanks to [Erik Ziegler](https://www.npmjs.com/~swederik) who support several [issues](https://groups.google.com/forum/#!forum/cornerstone-platform) during this path.

- [Aloïs Dreyfus](https://www.linkedin.com/in/alois-dreyfus) ([adreyfus](https://github.com/adreyfus))

- [Chris Hafey](https://www.linkedin.com/in/chafey/) ([chafey](https://github.com/chafey))

- [Danny Brown](http://dannyrb.com/) ([dannyrb](https://github.com/dannyrb))

- [Erik Ziegler](https://www.npmjs.com/~swederik) ([swederik](https://github.com/swederik))

- [Jason Hostetter](http://www.jasonhostetter.com/)

- [Marcelo Ribeiro](http://www.sysline.inf.br/) ([sysline](https://github.com/sysline))

- [Sébastien Jodogne](https://www.linkedin.com/in/jodogne/) ([jodogne](https://github.com/jodogne))

- [Steve Pieper](https://lmi.med.harvard.edu/people/steve-pieper)

### Team

Ou team brings everything together sharing ideas and the same purpose, developing even better work. In this section, we will nominate the full list of important people for this repository, as well as respective links.

#### Authors

- [Francisco Maria Calisto](https://web.tecnico.ulisboa.pt/francisco.calisto/) [[GitHub](https://github.com/FMCalisto) | [Linkedin](https://linkedin.com/in/fmcalisto/)]

#### Maintainers

- [Hugo Lencastre]() [[GitHub](https://github.com/HugoLencastre) | [Linkedin]()]

- [Nádia Mourão]() [[GitHub](https://github.com/nadia-mourao) | [Linkedin]()]

### Supporting

Our organization is a non-profit organization. However, we have many needs across our activity. From infrastructure to service needs, we need some time and contribution, as well as help, to support our team and projects.

<span class="image">
  <a href="https://opencollective.com/oppr" target="_blank">
    <img src="https://opencollective.com/oppr/tiers/backer.svg" width="220">
  </a>
</span>

#### Contributors

This project exists thanks to all the people who contribute. [[Contribute](CONTRIBUTING.md)].

#### Backers

Thank you to all our backers! 🙏 [[Become a backer](https://opencollective.com/oppr#backer)]

<span class="image">
  <a href="https://opencollective.com/oppr#backers" target="_blank">
    <img src="https://opencollective.com/oppr/backers.svg?width=890">
  </a>
</span>

#### Sponsors

Support this project by becoming a sponsor. Your logo will show up here with a link to your website. [[Become a sponsor](https://opencollective.com/oppr#sponsor)]

<span class="image">
  <a href="https://opencollective.com/oppr/sponsor/0/website" target="_blank">
    <img src="https://opencollective.com/oppr/sponsor/0/avatar.svg">
  </a>
</span>

<br />

<span class="image">
  <a href="http://www.fct.pt/" title="FCT" target="_blank">
    <img src="https://github.com/mida-project/meta/blob/master/brands/fct_footer.png" alt="fct" width="20%" />
  </a>
</span>
<span class="image">
  <a href="https://www.fccn.pt/en/" title="FCCN" target="_blank">
    <img src="https://github.com/mida-project/meta/blob/master/brands/fccn_footer.png" alt="fccn" width="20%" />
  </a>
</span>
<span class="image">
  <a href="https://www.ulisboa.pt/en/" title="ULisboa" target="_blank">
    <img src="https://github.com/mida-project/meta/blob/master/brands/ulisboa_footer.png" alt="ulisboa" width="20%" />
  </a>
</span>
<span class="image">
  <a href="http://tecnico.ulisboa.pt/" title="IST" target="_blank">
    <img src="https://github.com/mida-project/meta/blob/master/brands/ist_footer.png" alt="ist" width="20%" />
  </a>
</span>
<span class="image">
  <a href="http://hff.min-saude.pt/" title="HFF" target="_blank">
    <img src="https://github.com/mida-project/meta/blob/master/brands/hff_footer.png" alt="hff" width="20%" />
  </a>
</span>

##### Departments

<span class="image">
  <a href="http://dei.tecnico.ulisboa.pt" title="DEI" target="_blank">
    <img src="https://github.com/mida-project/meta/blob/master/brands/dei_footer.png" alt="dei" width="20%" />
  </a>
</span>
<span class="image">
  <a href="http://deec.tecnico.ulisboa.pt" title="DEEC" target="_blank">
    <img src="https://github.com/mida-project/meta/blob/master/brands/deec_footer.png" alt="dei" width="20%" />
  </a>
</span>

##### Laboratories

<span class="image">
  <a href="http://sipg.isr.tecnico.ulisboa.pt/" title="SIPG" target="_blank">
    <img src="https://github.com/mida-project/meta/blob/master/brands/sipg_footer.png" alt="sipg" width="20%" />
  </a>
</span>
<span class="image">
  <a href="http://welcome.isr.tecnico.ulisboa.pt/" title="ISR" target="_blank">
    <img src="https://github.com/mida-project/meta/blob/master/brands/isr-lisboa_footer.png" alt="isr" width="20%" />
  </a>
</span>
<span class="image">
  <a href="http://larsys.pt/" title="LARSys" target="_blank">
    <img src="https://github.com/mida-project/meta/blob/master/brands/larsys_footer.png" alt="larsys" width="20%" />
  </a>
</span>
<span class="image">
  <a href="https://www.m-iti.org/" title="M-ITI" target="_blank">
    <img src="https://github.com/mida-project/meta/blob/master/brands/iti_footer.png" alt="iti" width="20%" />
  </a>
</span>
<span class="image">
  <a href="http://www.inesc-id.pt/" title="INESC-ID" target="_blank">
    <img src="https://github.com/mida-project/meta/blob/master/brands/inesc-id_footer.png" alt="inesc-id" width="20%" />
  </a>
</span>

##### Domain

<span class="image">
  <a href="https://europa.eu/" title="EU" target="_blank">
    <img src="https://github.com/mida-project/meta/blob/master/brands/eu_footer.png" alt="eu" width="20%" />
  </a>
</span>
<span class="image">
  <a href="https://www.portugal.gov.pt/" title="Portugal" target="_blank">
    <img src="https://github.com/mida-project/meta/blob/master/brands/pt_footer.png" alt="pt" width="20%" />
  </a>
</span>
