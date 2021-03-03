# prometheus-vcd-sd

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/prometheus-vcd-sd) [![Build Status](https://img.shields.io/drone/build/rolehippie/prometheus-vcd-sd/master?logo=drone)](https://cloud.drone.io/rolehippie/prometheus-vcd-sd) [![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/prometheus-vcd-sd)](https://github.com/rolehippie/prometheus-vcd-sd/blob/master/LICENSE) 

Ansible role to install and configure a Prometheus vCloud service discovery. 

## Sponsor 

[![Proact Deutschland GmbH](https://proact.eu/wp-content/uploads/2020/03/proact-logo.png)](https://proact.eu) 

Building and improving this Ansible role have been sponsored by my employer **Proact Deutschland GmbH**.

## Table of content

* [Default Variables](#default-variables)
  * [prometheus_scrape_configs](#prometheus_scrape_configs)
  * [prometheus_vcd_sd_config_path](#prometheus_vcd_sd_config_path)
  * [prometheus_vcd_sd_credentials](#prometheus_vcd_sd_credentials)
  * [prometheus_vcd_sd_credentials_file](#prometheus_vcd_sd_credentials_file)
  * [prometheus_vcd_sd_download](#prometheus_vcd_sd_download)
  * [prometheus_vcd_sd_group](#prometheus_vcd_sd_group)
  * [prometheus_vcd_sd_log_level](#prometheus_vcd_sd_log_level)
  * [prometheus_vcd_sd_log_pretty](#prometheus_vcd_sd_log_pretty)
  * [prometheus_vcd_sd_output_file](#prometheus_vcd_sd_output_file)
  * [prometheus_vcd_sd_output_refresh](#prometheus_vcd_sd_output_refresh)
  * [prometheus_vcd_sd_owner](#prometheus_vcd_sd_owner)
  * [prometheus_vcd_sd_version](#prometheus_vcd_sd_version)
  * [prometheus_vcd_sd_web_address](#prometheus_vcd_sd_web_address)
  * [prometheus_vcd_sd_web_path](#prometheus_vcd_sd_web_path)
* [Dependencies](#dependencies)
* [License](#license)
* [Author](#author)

---

## Default Variables

### prometheus_scrape_configs

#### Example usage

```YAML
prometheus_vcd_sd_credentials:
  - project: example
    url: https://vcd.example.com/api
    insecure: False
    username: username
    password: password
    org: DE-XX1
    vdc: DE-XX1-NUE-A1
  - project: foobar
    url: https://vcd.foobar.com/api
    insecure: True
    username: username
    password: password
    org: DE-YY1
    vdc: DE-YY1-NUE-A1
```

### prometheus_vcd_sd_config_path

Path to vCloud Director configuration file

### prometheus_vcd_sd_credentials

List of credentials to access vCloud Director

#### Default value

```YAML
prometheus_vcd_sd_credentials: []
```

### prometheus_vcd_sd_credentials_file

#### Default value

```YAML
prometheus_vcd_sd_credentials_file: /etc/prometheus-vcd-sd/credentials.json
```

### prometheus_vcd_sd_download

URL to the archive of the release to install

#### Default value

```YAML
prometheus_vcd_sd_download: https://github.com/promhippie/prometheus-vcd-sd/releases/download/v{{
  prometheus_vcd_sd_version }}/prometheus-vcd-sd-{{ prometheus_vcd_sd_version }}-linux-amd64
```

### prometheus_vcd_sd_group

Group of the configuration, should be the prometheus group

#### Default value

```YAML
prometheus_vcd_sd_group: prometheus
```

### prometheus_vcd_sd_log_level

Only log messages with given severity

#### Default value

```YAML
prometheus_vcd_sd_log_level: info
```

### prometheus_vcd_sd_log_pretty

Enable pretty messages for logging

#### Default value

```YAML
prometheus_vcd_sd_log_pretty: true
```

### prometheus_vcd_sd_output_file

Path to write the file_sd config

#### Default value

```YAML
prometheus_vcd_sd_output_file: /etc/prometheus/vcd.json
```

### prometheus_vcd_sd_output_refresh

Discovery refresh interval in seconds

#### Default value

```YAML
prometheus_vcd_sd_output_refresh: 300
```

### prometheus_vcd_sd_owner

Owner of the configuration, should be the prometheus user

#### Default value

```YAML
prometheus_vcd_sd_owner: prometheus
```

### prometheus_vcd_sd_version

Version of the release to install

#### Default value

```YAML
prometheus_vcd_sd_version: 0.1.1
```

### prometheus_vcd_sd_web_address

Address to bind the metrics server

#### Default value

```YAML
prometheus_vcd_sd_web_address: 127.0.0.1:9000
```

### prometheus_vcd_sd_web_path

Path to bind the metrics server

#### Default value

```YAML
prometheus_vcd_sd_web_path: /metrics
```

## Dependencies

* [rolehippie.docker](https://github.com/rolehippie/docker)

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
