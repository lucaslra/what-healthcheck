<h1 align="center">what-healthcheck</h1>

<p align="center">
   <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat" alt="">
   <a href="https://github.com/peterbuga/what-healthcheck/actions"><img src="https://img.shields.io/github/actions/workflow/status/peterbuga/what-healthcheck/pages/pages-build-deployment" alt="Github Actions"></a>
   <a href="https://github.com/peterbuga/what-healthcheck/blob/master/LICENCE"><img src="https://img.shields.io/github/license/peterbuga/what-healthcheck.svg" alt="LICENCE"></a>
</p>

<p align="center">Unopinionated list of self-hosted applications healthchecks.</p>


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

The table is bound to change as more details need to be further included.

| Name        | Repository                                                                       | Version*    | Health Endpoint** | Status | Method | Headers | Remarks |
|-------------|----------------------------------------------------------------------------------|-------------|-------------------|--------|--------|---------|---------|
| Sonarr      | [github.com/Sonarr/Sonarr](https://github.com/Sonarr/Sonarr)                     | `>4.0.5`    | `/ping`           | 200    | GET    |         |         |
| Radarr      | [github.com/Radarr/Radarr](https://github.com/Radarr/Radarr)                     | `>5.20.2`   | `/ping`           | 200    | GET    |         |         |
| Lidarr      | [github.com/Lidarr/Lidarr](https://github.com/Lidarr/Lidarr)                     | `>2.3.3`    | `/ping`           | 200    | GET    |         |         |
| Prowlarr    | [github.com/Prowlarr/Prowlarr](https://github.com/Prowlarr/Prowlarr)             | `>1.27.3`   | `/ping`           | 200    | GET    |         |         |
| AdguardHome | [github.com/AdguardTeam/AdGuardHome](https://github.com/AdguardTeam/AdGuardHome) | `>0.107.56` | `/control/status` | 200    | GET    |         |         |
