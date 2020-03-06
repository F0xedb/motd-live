[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]

<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/F0xedb/motd-live">
    <img src="https://tos.odex.be/images/logo.svg" alt="Logo" width="150" height="200">
  </a>

  <h3 align="center">Update-MOTD</h3>

  <p align="center">
    Easily generate nice and life updating motd
    <br />
    <a href="https://github.com/F0xedb/motd-live"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/F0xedb/motd-live">View Demo</a>
    ·
    <a href="https://github.com/F0xedb/motd-live/issues">Report Bug</a>
    ·
    <a href="https://github.com/F0xedb/motd-live/issues">Request Feature</a>
  </p>
</p>

<!-- TABLE OF CONTENTS -->

## Table of Contents

- [About the Project](#about-the-project)
  - [Built With](#built-with)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)
- [Acknowledgements](#acknowledgements)

<!-- ABOUT THE PROJECT -->

## About The Project

MOTD is a life updating message of the day script extending the update-motd framework developed by canonical
[MOTD screenshot](images/motd-example.png)

<!-- GETTING STARTED -->

## Getting Started

### Prerequisites

We only have one dependency which is cron

```sh
pacman -Syu cronie
```

### Installation

1. Clone the motd

```sh
git clone https://github.com/F0xedb/motd-live.git
```

2. Install packages

```sh
pacman -Syu cronie
```

3. Add the cronfile to /etc/cron.d

```sh
cp motd /etc/cron.d
```

4. Move the motd-live script to /usr/bin

```sh
cp motd-live-cm /usr/bin/motd-live
```

5. Add all other files to the /etc/motd-live directory

```sh
mkdir -p /etc/motd-live
cp -r . /etc/motd-live
```

6. Start the cron service

```sh
systemctl start cronie
systemctl enable cronie
```

7. Test if the cronjob is working

```sh
cat /etc/motd # this should output the correct information
```

<!-- USAGE EXAMPLES -->

## Usage

All you have to do is add shell scripts in the `/etc/motd-live directory`.
Each file will be executed and then appended to the `/etc/motd` file to generate the final output.
It works much like `update-motd` from ubuntu but without much of their dependencies for easier use between more operating systems.
if you want a script that should not be included in the final motd add then to the `/etc/motd-live/scripts` directory

If you wish to manually update the `/etc/motd` file run the command motd-live to update it.
Each new ssh login should then display the updated motd file.

_For more examples, please refer to the [Documentation](https://github.com/F0xedb/motd-live)_

<!-- ROADMAP -->

## Roadmap

See the [open issues](https://github.com/F0xedb/motd-live/issues) for a list of proposed features (and known issues).

<!-- CONTRIBUTING -->

## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<!-- LICENSE -->

## License

Distributed under the MIT License. See `LICENSE` for more information.

<!-- CONTACT -->

## Contact

F0xedb - tom@odex.be

Project Link: [https://github.com/F0xedb/motd-live](https://github.com/F0xedb/motd-live)

<!-- ACKNOWLEDGEMENTS -->

## Acknowledgements

- [F0xedb](https://github.com/F0xedb/motd-live)

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[contributors-shield]: https://img.shields.io/github/contributors/F0xedb/motd.svg?style=flat-square
[contributors-url]: https://github.com/F0xedb/motd-live/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/F0xedb/motd.svg?style=flat-square
[forks-url]: https://github.com/F0xedb/motd-live/network/members
[stars-shield]: https://img.shields.io/github/stars/F0xedb/motd.svg?style=flat-square
[stars-url]: https://github.com/F0xedb/motd-live/stargazers
[issues-shield]: https://img.shields.io/github/issues/F0xedb/motd.svg?style=flat-square
[issues-url]: https://github.com/F0xedb/motd-live/issues
[license-shield]: https://img.shields.io/github/license/F0xedb/motd.svg?style=flat-square
[license-url]: https://github.com/F0xedb/motd-live/blob/master/LICENSE.txt
[product-screenshot]: https://tos.odex.be/images/logo.svg
