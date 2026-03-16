# PA TSA High School Cybersecurity CTF

This repository contains the challenge content, platform configuration, and event materials for the Pennsylvania TSA High School Cybersecurity state conference competition.

## Purpose

This repo is used to:

- store challenge definitions for the competition
- track setup and deployment guidance for CTFd
- manage custom informational pages shown to participants
- document rules, expectations, and event logistics
- support local testing before the state conference

## Repository Layout

- [challenges/](challenges/) - CTF challenge definitions and related assets
- [docs/setup.md](docs/setup.md) - local setup and deployment guidance
- [pages/](pages/) - custom CTFd pages for participants

## Challenges Content
All challenges that can be used for a state conferences are located in the `challenges` folder.
They are in a format that CTFd can import using the [`ctfcli`](https://github.com/CTFd/ctfcli) tool.

For details on available challenges, refer to the [challenges/README.md](challenges/README.md) file.

## Local Development

This project uses [CTFd](https://ctfd.io/) for local testing.

See [docs/setup.md](docs/setup.md) for full instructions.

### Quick start with Docker

```shell
docker run -p 8000:8000 -it ctfd/ctfd
```

### Quick start with Podman

```shell
podman run -p 8000:8000 -it ctfd/ctfd
```

After CTFd is running, complete the initial web setup, then use the configuration described in docs/setup.md.

## Competition Pages
The repository includes custom pages intended for the event platform:

- [pages/index.md](pages/index.md) - landing page
- [pages/rules.md](pages/rules.md) - official event rules
- [pages/read_read_read.md](pages/read_read_read.md) - participant prep guidance
- [pages/ethics_safety_use.md](pages/read_read_read.md) - ethics, safety, and acceptable use policy

## Event Operations
This repository supports two main use cases:

1. Local testing
   - validate challenge content
   - verify scoring and flag behavior
   - preview participant-facing pages
2. State conference deployment
   - prepare the final competition instance
   - publish challenge set and event pages
   - provide rule and safety documentation to teams

## Suggested Workflow
1. Start a local CTFd instance
2. Complete the CTFd admin setup
3. Configure access as described in docs/setup.md
4. Add or update challenges in challenges/
5. Review participant-facing content in pages/
6. Test challenge solves, scoring, and hints before event release

## Notes
- [docs/setup.md](docs/setup.md) is the primary setup reference
- .gitignore currently excludes local .ctf/ CLI data
- Review all participant-facing text before the conference for accuracy and event readiness

## License
This project is licensed under the terms in [LICENSE](LICENSE).