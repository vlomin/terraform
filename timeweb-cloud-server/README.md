<!-- BEGIN_TF_DOCS -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 1.3 |
| <a name="requirement_twc"></a> [twc](#requirement\_twc) | >= 1.1.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_twc"></a> [twc](#provider\_twc) | >= 1.1.0 |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| twc_floating_ip.this | resource |
| twc_server.this | resource |
| twc_ssh_key.this | resource |
| twc_configurator.this | data source |
| twc_os.this | data source |
| twc_presets.this | data source |
| twc_projects.this | data source |
| twc_software.this | data source |
| twc_ssh_keys.this | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_availability_zone"></a> [availability\_zone](#input\_availability\_zone) | Availability zone for cloud server and floating ip | `string` | `"spb-3"` | no |
| <a name="input_cloud_init"></a> [cloud\_init](#input\_cloud\_init) | Cloud-init script path to file | <pre>object({<br/>    file = string<br/>    vars = optional(map(string))<br/>  })</pre> | `null` | no |
| <a name="input_configurator"></a> [configurator](#input\_configurator) | Settings for the server with configurator | <pre>object({<br/>    cpu  = number<br/>    ram  = number<br/>    disk = number<br/>  })</pre> | `null` | no |
| <a name="input_cpu_frequency"></a> [cpu\_frequency](#input\_cpu\_frequency) | Current CPU frequency of server (2.8, 3.3, 5) | `number` | `3.3` | no |
| <a name="input_create_floating_ip"></a> [create\_floating\_ip](#input\_create\_floating\_ip) | Create or not externam ip for cloud server | `bool` | `false` | no |
| <a name="input_disk_type"></a> [disk\_type](#input\_disk\_type) | Disk type for the created server (ssd, nvme, hdd) | `string` | `null` | no |
| <a name="input_location"></a> [location](#input\_location) | Location for the server (ru-1, ru-2, pl-1, kz-1) | `string` | `null` | no |
| <a name="input_name"></a> [name](#input\_name) | Server name | `string` | `"Managed by terraform"` | no |
| <a name="input_os"></a> [os](#input\_os) | Information about specified OS | <pre>object({<br/>    name    = string<br/>    version = string<br/>  })</pre> | <pre>{<br/>  "name": "ubuntu",<br/>  "version": "22.04"<br/>}</pre> | no |
| <a name="input_preset"></a> [preset](#input\_preset) | Settings for the server with preset | <pre>object({<br/>    cpu  = number<br/>    ram  = number<br/>    disk = number<br/><br/>    price = optional(object({<br/>      min = number<br/>      max = number<br/>    }))<br/>  })</pre> | `null` | no |
| <a name="input_project_name"></a> [project\_name](#input\_project\_name) | Name of existing project | `string` | `null` | no |
| <a name="input_software"></a> [software](#input\_software) | Information about specified software | <pre>object({<br/>    name       = string<br/>    os_family  = string<br/>    os_name    = string<br/>    os_version = string<br/>  })</pre> | <pre>{<br/>  "name": "Wireguard-GUI",<br/>  "os_family": "linux",<br/>  "os_name": "ubuntu",<br/>  "os_version": "22.04"<br/>}</pre> | no |
| <a name="input_ssh_keys"></a> [ssh\_keys](#input\_ssh\_keys) | List of names SSH Keys for server | `list(string)` | `null` | no |
| <a name="input_ssh_keys_paths"></a> [ssh\_keys\_paths](#input\_ssh\_keys\_paths) | Local paths of SSH Keys for server | <pre>list(object({<br/>    name = string<br/>    path = string<br/>  }))</pre> | `null` | no |
| <a name="input_timeweb_token"></a> [timeweb\_token](#input\_timeweb\_token) | TimeWebCloud Token | `string` | `null` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_server_cloud_init"></a> [server\_cloud\_init](#output\_server\_cloud\_init) | Return cloud init script |
| <a name="output_server_id"></a> [server\_id](#output\_server\_id) | Return server id |
| <a name="output_server_name"></a> [server\_name](#output\_server\_name) | Return server name |
| <a name="output_server_network"></a> [server\_network](#output\_server\_network) | Return all information about server network |
| <a name="output_server_public_ip"></a> [server\_public\_ip](#output\_server\_public\_ip) | Return server public IP |
<!-- END_TF_DOCS -->