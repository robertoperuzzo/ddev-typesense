[![add-on registry](https://img.shields.io/badge/DDEV-Add--on_Registry-blue)](https://addons.ddev.com)
[![tests](https://github.com/lussoluca/ddev-typesense/actions/workflows/tests.yml/badge.svg)](https://github.com/lussoluca/ddev-typesense/actions/workflows/tests.yml)
[![last commit](https://img.shields.io/github/last-commit/lussoluca/ddev-typesense)](https://github.com/lussoluca/ddev-typesense/commits)
[![release](https://img.shields.io/github/v/release/lussoluca/ddev-typesense)](https://github.com/lussoluca/ddev-typesense/releases/latest)

# DDEV Typesense Add-On

## Overview

This add-on integrates Typesense into your [DDEV](https://ddev.com/) project,
using the current stable release of the Typesense Docker image.

## Installation

With DDEV installed, run this command:

```bash
ddev add-on get lussoluca/ddev-typesense
ddev restart
```

After installation, make sure to commit the `.ddev` directory to version control.

## Configuration



## Usage

| Command | Description |
| ------- | ----------- |
| `ddev describe` | View service status and used ports for DDEV Typesense Add-On |
| `ddev logs -s ddev-typesense` | Check DDEV Typesense Add-On logs |

## Advanced Customization

The Typesense container is reached at hostname: `https://(DDEV_HOSTNAME)`, port: 8109.

The default API key for Typesense is `ddev`. You can provide your own by adding
the variable `TYPESENSE_API_KEY` to the _dotenv_ file  `.ddev/.env.typesense`
in your project.

```bash
ddev dotenv set .ddev/.env.typesense --typesense-api-key="my_api_key_value"
ddev add-on get lussoluca/ddev-typesense
ddev restart
```

To change the Docker image:

```bash
ddev dotenv set .ddev/.env.typesense --typesense-docker-image-tag="30.0.rc2"
ddev add-on get lussoluca/ddev-typesense
ddev restart
```

Make sure to commit the `.ddev/.env.typesense` file to version control.

All customization options (use with caution):

| Variable | Flag | Default |
| -------- | ---- | ------- |
| `TYPESENSE_API_KEY` | `--typesense-api-key` | `ddev` |
| `TYPESENSE_DOCKER_IMAGE_TAG` | `--typesense-docker-image-tag` | `28.0` |

## Admin Dashboard

This DDEV add-on comes bundled with the **Typesense Admin Dashboard** by [bfritscher](https://github.com/bfritscher/typesense-dashboard).

The dashboard provides a user-friendly interface to browse collections, inspect schemas, and debug search queries.

To access the dashboard, open the following URL in your browser:

`https://<DDEV_HOSTNAME>:8111`

# Drupal and Search API

For Drupal users, you can integrate with Typesense using the
[Search API](https://www.drupal.org/project/search_api) module together with the
[Search API Typesense](https://www.drupal.org/project/search_api_typesense).
This allows you to connect your Drupal site directly to the running Typesense instance.

## How to debug tests (Github Actions)

If you need to debug your tests running in GitHub Actions, look at the
[README_DEBUG.md](https://git.new/QUFopEr).

## Credits

> Originally Contributed by [kevinquillen](https://github.com/kevinquillen), then adapted to work with latest Typesense server over HTTPS.

**Contributed and maintained by [@lussoluca](https://github.com/lussoluca)**

