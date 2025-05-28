# what-healthcheck <img src="assets/image/what-healthcheck-logo.png" alt="what-healthcheck-logo" title="feishin" align="right" height="95px" />

<p align="left">
   <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat" alt="">
   <a href="https://github.com/peterbuga/what-healthcheck/actions"><img src="https://img.shields.io/github/actions/workflow/status/peterbuga/what-healthcheck/pages/pages-build-deployment" alt="Github Actions"></a>
   <a href="https://github.com/peterbuga/what-healthcheck/blob/master/LICENSE"><img src="https://img.shields.io/github/license/peterbuga/what-healthcheck.svg" alt="LICENSE"></a>
</p>

<p align="center">Unopinionated list of self-hosted applications health checks.</p>


### What is this?
A (growing) list of healthchecks for self-hosted software, so it can help set up faster health observability of said applications. 

The list can be used to add uptime check to tools like [Traefik](https://traefik.io/) / [UptimeKuma](https://uptimekuma.org/) / [Gatus](https://gatus.io/) / and many more similar others.

### Why is this?
While trying to migrate to a different health monitoring system, I realized a lot of health endpoints are either not-available or not listed and hidden into the code outside any documentation and usually available post a raised issue or PR.

Simply monitoring the base target (ex: `/`), although it works just fine, might not the best option if more services are piling up and create a lot of internal traffic and resource processing to serve the main page.  

### How to add new entries
Fields descriptions:

- *Name* - official application name, to identify and search them easier. could be more listed if spelling alternatives exists.
- *Repository* (mandatory) - needs to be a hyperlink of the source code (stripping `https://` for anchor) and/or official website. multiple entries can be added for listing active forks (if forks are too different they should be split in a separate entry)
- *Version* (mandatory) - should list a minimum confirmed version the health endpoint works. can also be a range ex: `2.3.0-4.7.0` or `>2.3.0` format, for different updated health endpoint on a future version a new entry must be created.
- *Health Endpoint* (mandatory)
- *Status* (mandatory) - expected status code
- *Method* (mandatory) - method used to test the health endpoint (ex: `GET POST HEAD`)
- *Headers* - headers required to successfully test the endpoint (if any)
- *Response* - sample response (if any)
- *Remarks* - additional information (if any)

#### Notice
This is by far an incomplete list, any raised issue with or w/out a new entry is more than welcomed. PRs even more!  

*The information table below is bound to change as more details need to be further included.*

| Name                | Repository                                                                               | Version*    | Health Endpoint**                        | Status | Method | Headers                                                                    | Remarks           |
|---------------------|------------------------------------------------------------------------------------------|-------------|------------------------------------------|--------|--------|----------------------------------------------------------------------------|-------------------|
| 2FAuth              | [github.com/Bubka/2FAuth](https://github.com/Bubka/2FAuth)                               | `>5.5.0`    | `/up`                                    | 200    | GET    |                                                                            |                   |
| Sonarr              | [github.com/Sonarr/Sonarr](https://github.com/Sonarr/Sonarr)                             | `>4.0.5`    | `/ping`                                  | 200    | GET    |                                                                            |                   |
| Radarr              | [github.com/Radarr/Radarr](https://github.com/Radarr/Radarr)                             | `>5.20.2`   | `/ping`                                  | 200    | GET    |                                                                            |                   |
| Lidarr              | [github.com/Lidarr/Lidarr](https://github.com/Lidarr/Lidarr)                             | `>2.3.3`    | `/ping`                                  | 200    | GET    |                                                                            |                   |
| Prowlarr            | [github.com/Prowlarr/Prowlarr](https://github.com/Prowlarr/Prowlarr)                     | `>1.27.3`   | `/ping`                                  | 200    | GET    |                                                                            |                   |
| AdGuardHome         | [github.com/AdguardTeam/AdGuardHome](https://github.com/AdguardTeam/AdGuardHome)         | `>0.107.56` | `/control/status`                        | 200    | GET    |                                                                            |                   |
| Argus               | [github.com/release-argus/Argus](https://github.com/release-argus/Argus)                 | `>0.20.0`   | `/api/v1/healthcheck`                    | 200    | GET    |                                                                            |                   |
| Apprise API         | [github.com/caronc/apprise-api](https://github.com/caronc/apprise-api)                   | `>1.2.0`    | `/status`                                | 200    | GET    |                                                                            |                   |
| Atuin               | [github.com/atuinsh/atuin](https://github.com/atuinsh/atuin)                             | `>18.6.0`   | `/healthz`                               | 200    | GET    |                                                                            |                   |
| Authelia            | [github.com/authelia/authelia](https://github.com/authelia/authelia)                     | `>4.39.4`   | `/api/health`                            | 200    | GET    |                                                                            |                   |
| Backrest            | [github.com/garethgeorge/backrest](https://github.com/garethgeorge/backrest)             | `>1.8.1`    | `/v1.Backrest/GetConfig`                 | 200    | POST   | content-type: application/proto                                            |                   |
| Beszel              | [github.com/henrygd/beszel](https://github.com/henrygd/beszel)                           | `>0.11.1`   | `/api/health`                            | 200    | GET    |                                                                            |                   |
| Bonob               | [github.com/simojenki/bonob](https://github.com/simojenki/bonob)                         | `>0.9.0`    | `/ws/sonos`                              | 200    | GET    |                                                                            |                   |
| ChangeDetection     | [github.com/dgtlmoon/changedetection.io](https://github.com/dgtlmoon/changedetection.io) | `>0.49.17`  | `/api/v1/systeminfo`                     | 200    | GET    |                                                                            |                   |
| Chartbrew           | [github.com/chartbrew/chartbrew](https://github.com/chartbrew/chartbrew)                 | `>4.0.0`    | `/update`                                | 200    | GET    |                                                                            | for API component |
| Cronicle            | [github.com/jhuckaby/Cronicle](https://github.com/jhuckaby/Cronicle)                     | `>0.9.77`   | `/api/app/ping`                          | 200    | GET    |                                                                            |                   |
| DelugeVPN           | [github.com/binhex/arch-delugevpn](https://github.com/binhex/arch-delugevpn)             | `>2.1.1`    | `/images/s.gif`                          | 200    | GET    |                                                                            |                   |
| Gatus               | [github.com/TwiN/gatus](https://github.com/TwiN/gatus)                                   | `>5.17.0`   | `/health`                                | 200    | GET    |                                                                            |                   |
| Gitea               | [github.com/go-gitea/gitea](https://github.com/go-gitea/gitea)                           | `>1.23.8`   | `/api/healthz`                           | 200    | GET    |                                                                            |                   |
| Grafana             | [github.com/grafana/grafana](https://github.com/grafana/grafana)                         | `>12.0.0`   | `/api/health`                            | 200    | GET    |                                                                            |                   |
| HomeAssistant Core  | [github.com/home-assistant/core](https://github.com/home-assistant/core)                 | `>2025.5.3` | `/api/`                                  | 401    | GET    | no real live-endpoint. one could create an empty API webhook to return 200 |                   |

\* it's highly likely the health endpoint will work for app versions **not** mentioned here, the listed ones are confirmed to work.

\*\* not all applications define a true health endpoint. in order to have a minimum live-ness "*endpoint*", the smallest available request was selected.
