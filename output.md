## terraform init

```
[ilker@ilker-pc terraform-gke]$ terraform init

Initializing the backend...

Initializing provider plugins...
- Finding latest version of hashicorp/google...
- Installing hashicorp/google v3.47.0...
- Installed hashicorp/google v3.47.0 (signed by HashiCorp)

The following providers do not have any version constraints in configuration,
so the latest version was installed.

To prevent automatic upgrades to new major versions that may contain breaking
changes, we recommend adding version constraints in a required_providers block
in your configuration, with the constraint strings suggested below.

* hashicorp/google: version = "~> 3.47.0"

Terraform has been successfully initialized!

You may now begin working with Terraform. Try running "terraform plan" to see
any changes that are required for your infrastructure. All Terraform commands
should now work.

If you ever set or change modules or backend configuration for Terraform,
rerun this command to reinitialize your working directory. If you forget, other
commands will detect it and remind you to do so if necessary.
```

## terraform plan

```
[ilker@ilker-pc terraform-gke]$ terraform plan
Refreshing Terraform state in-memory prior to plan...
The refreshed state will be used to calculate this plan, but will not be
persisted to local or remote state storage.


------------------------------------------------------------------------

An execution plan has been generated and is shown below.
Resource actions are indicated with the following symbols:
  + create

Terraform will perform the following actions:

  # google_container_cluster.default will be created
  + resource "google_container_cluster" "default" {
      + cluster_ipv4_cidr           = (known after apply)
      + default_max_pods_per_node   = (known after apply)
      + description                 = "Demo GKE Cluster"
      + enable_binary_authorization = false
      + enable_kubernetes_alpha     = false
      + enable_legacy_abac          = false
      + enable_shielded_nodes       = false
      + endpoint                    = (known after apply)
      + id                          = (known after apply)
      + initial_node_count          = 1
      + instance_group_urls         = (known after apply)
      + label_fingerprint           = (known after apply)
      + location                    = "europe-west4"
      + logging_service             = (known after apply)
      + master_version              = (known after apply)
      + monitoring_service          = (known after apply)
      + name                        = "demo-cluster"
      + network                     = "default"
      + node_locations              = (known after apply)
      + node_version                = (known after apply)
      + operation                   = (known after apply)
      + project                     = "ilkerispir"
      + remove_default_node_pool    = true
      + self_link                   = (known after apply)
      + services_ipv4_cidr          = (known after apply)
      + subnetwork                  = (known after apply)

      + addons_config {
          + cloudrun_config {
              + disabled           = (known after apply)
              + load_balancer_type = (known after apply)
            }

          + horizontal_pod_autoscaling {
              + disabled = (known after apply)
            }

          + http_load_balancing {
              + disabled = (known after apply)
            }

          + network_policy_config {
              + disabled = (known after apply)
            }
        }

      + authenticator_groups_config {
          + security_group = (known after apply)
        }

      + cluster_autoscaling {
          + enabled = (known after apply)

          + auto_provisioning_defaults {
              + oauth_scopes    = (known after apply)
              + service_account = (known after apply)
            }

          + resource_limits {
              + maximum       = (known after apply)
              + minimum       = (known after apply)
              + resource_type = (known after apply)
            }
        }

      + database_encryption {
          + key_name = (known after apply)
          + state    = (known after apply)
        }

      + master_auth {
          + client_certificate     = (known after apply)
          + client_key             = (sensitive value)
          + cluster_ca_certificate = (known after apply)

          + client_certificate_config {
              + issue_client_certificate = false
            }
        }

      + network_policy {
          + enabled  = (known after apply)
          + provider = (known after apply)
        }

      + node_config {
          + disk_size_gb      = (known after apply)
          + disk_type         = (known after apply)
          + guest_accelerator = (known after apply)
          + image_type        = (known after apply)
          + labels            = (known after apply)
          + local_ssd_count   = (known after apply)
          + machine_type      = (known after apply)
          + metadata          = (known after apply)
          + min_cpu_platform  = (known after apply)
          + oauth_scopes      = (known after apply)
          + preemptible       = (known after apply)
          + service_account   = (known after apply)
          + tags              = (known after apply)
          + taint             = (known after apply)

          + shielded_instance_config {
              + enable_integrity_monitoring = (known after apply)
              + enable_secure_boot          = (known after apply)
            }

          + workload_metadata_config {
              + node_metadata = (known after apply)
            }
        }

      + node_pool {
          + initial_node_count  = (known after apply)
          + instance_group_urls = (known after apply)
          + max_pods_per_node   = (known after apply)
          + name                = (known after apply)
          + name_prefix         = (known after apply)
          + node_count          = (known after apply)
          + node_locations      = (known after apply)
          + version             = (known after apply)

          + autoscaling {
              + max_node_count = (known after apply)
              + min_node_count = (known after apply)
            }

          + management {
              + auto_repair  = (known after apply)
              + auto_upgrade = (known after apply)
            }

          + node_config {
              + disk_size_gb      = (known after apply)
              + disk_type         = (known after apply)
              + guest_accelerator = (known after apply)
              + image_type        = (known after apply)
              + labels            = (known after apply)
              + local_ssd_count   = (known after apply)
              + machine_type      = (known after apply)
              + metadata          = (known after apply)
              + min_cpu_platform  = (known after apply)
              + oauth_scopes      = (known after apply)
              + preemptible       = (known after apply)
              + service_account   = (known after apply)
              + tags              = (known after apply)
              + taint             = (known after apply)

              + shielded_instance_config {
                  + enable_integrity_monitoring = (known after apply)
                  + enable_secure_boot          = (known after apply)
                }

              + workload_metadata_config {
                  + node_metadata = (known after apply)
                }
            }

          + upgrade_settings {
              + max_surge       = (known after apply)
              + max_unavailable = (known after apply)
            }
        }

      + release_channel {
          + channel = (known after apply)
        }
    }

  # google_container_node_pool.default will be created
  + resource "google_container_node_pool" "default" {
      + cluster             = "demo-cluster"
      + id                  = (known after apply)
      + initial_node_count  = (known after apply)
      + instance_group_urls = (known after apply)
      + location            = "europe-west4"
      + max_pods_per_node   = (known after apply)
      + name                = "demo-cluster-node-pool"
      + name_prefix         = (known after apply)
      + node_count          = 1
      + node_locations      = (known after apply)
      + project             = "ilkerispir"
      + version             = (known after apply)

      + management {
          + auto_repair  = (known after apply)
          + auto_upgrade = (known after apply)
        }

      + node_config {
          + disk_size_gb      = (known after apply)
          + disk_type         = (known after apply)
          + guest_accelerator = (known after apply)
          + image_type        = (known after apply)
          + labels            = (known after apply)
          + local_ssd_count   = (known after apply)
          + machine_type      = "n1-standard-1"
          + metadata          = {
              + "disable-legacy-endpoints" = "true"
            }
          + oauth_scopes      = [
              + "https://www.googleapis.com/auth/logging.write",
              + "https://www.googleapis.com/auth/monitoring",
            ]
          + preemptible       = true
          + service_account   = (known after apply)
          + taint             = (known after apply)

          + shielded_instance_config {
              + enable_integrity_monitoring = (known after apply)
              + enable_secure_boot          = (known after apply)
            }

          + workload_metadata_config {
              + node_metadata = (known after apply)
            }
        }

      + upgrade_settings {
          + max_surge       = (known after apply)
          + max_unavailable = (known after apply)
        }
    }

Plan: 2 to add, 0 to change, 0 to destroy.

------------------------------------------------------------------------

Note: You didn't specify an "-out" parameter to save this plan, so Terraform
can't guarantee that exactly these actions will be performed if
"terraform apply" is subsequently run.
```

## terraform apply

```
[ilker@ilker-pc terraform-gke]$ terraform apply

An execution plan has been generated and is shown below.
Resource actions are indicated with the following symbols:
  + create

Terraform will perform the following actions:

  # google_container_cluster.default will be created
  + resource "google_container_cluster" "default" {
      + cluster_ipv4_cidr           = (known after apply)
      + default_max_pods_per_node   = (known after apply)
      + description                 = "Demo GKE Cluster"
      + enable_binary_authorization = false
      + enable_kubernetes_alpha     = false
      + enable_legacy_abac          = false
      + enable_shielded_nodes       = false
      + endpoint                    = (known after apply)
      + id                          = (known after apply)
      + initial_node_count          = 1
      + instance_group_urls         = (known after apply)
      + label_fingerprint           = (known after apply)
      + location                    = "europe-west4"
      + logging_service             = (known after apply)
      + master_version              = (known after apply)
      + monitoring_service          = (known after apply)
      + name                        = "demo-cluster"
      + network                     = "default"
      + node_locations              = (known after apply)
      + node_version                = (known after apply)
      + operation                   = (known after apply)
      + project                     = "ilkerispir"
      + remove_default_node_pool    = true
      + self_link                   = (known after apply)
      + services_ipv4_cidr          = (known after apply)
      + subnetwork                  = (known after apply)

      + addons_config {
          + cloudrun_config {
              + disabled           = (known after apply)
              + load_balancer_type = (known after apply)
            }

          + horizontal_pod_autoscaling {
              + disabled = (known after apply)
            }

          + http_load_balancing {
              + disabled = (known after apply)
            }

          + network_policy_config {
              + disabled = (known after apply)
            }
        }

      + authenticator_groups_config {
          + security_group = (known after apply)
        }

      + cluster_autoscaling {
          + enabled = (known after apply)

          + auto_provisioning_defaults {
              + oauth_scopes    = (known after apply)
              + service_account = (known after apply)
            }

          + resource_limits {
              + maximum       = (known after apply)
              + minimum       = (known after apply)
              + resource_type = (known after apply)
            }
        }

      + database_encryption {
          + key_name = (known after apply)
          + state    = (known after apply)
        }

      + master_auth {
          + client_certificate     = (known after apply)
          + client_key             = (sensitive value)
          + cluster_ca_certificate = (known after apply)

          + client_certificate_config {
              + issue_client_certificate = false
            }
        }

      + network_policy {
          + enabled  = (known after apply)
          + provider = (known after apply)
        }

      + node_config {
          + disk_size_gb      = (known after apply)
          + disk_type         = (known after apply)
          + guest_accelerator = (known after apply)
          + image_type        = (known after apply)
          + labels            = (known after apply)
          + local_ssd_count   = (known after apply)
          + machine_type      = (known after apply)
          + metadata          = (known after apply)
          + min_cpu_platform  = (known after apply)
          + oauth_scopes      = (known after apply)
          + preemptible       = (known after apply)
          + service_account   = (known after apply)
          + tags              = (known after apply)
          + taint             = (known after apply)

          + shielded_instance_config {
              + enable_integrity_monitoring = (known after apply)
              + enable_secure_boot          = (known after apply)
            }

          + workload_metadata_config {
              + node_metadata = (known after apply)
            }
        }

      + node_pool {
          + initial_node_count  = (known after apply)
          + instance_group_urls = (known after apply)
          + max_pods_per_node   = (known after apply)
          + name                = (known after apply)
          + name_prefix         = (known after apply)
          + node_count          = (known after apply)
          + node_locations      = (known after apply)
          + version             = (known after apply)

          + autoscaling {
              + max_node_count = (known after apply)
              + min_node_count = (known after apply)
            }

          + management {
              + auto_repair  = (known after apply)
              + auto_upgrade = (known after apply)
            }

          + node_config {
              + disk_size_gb      = (known after apply)
              + disk_type         = (known after apply)
              + guest_accelerator = (known after apply)
              + image_type        = (known after apply)
              + labels            = (known after apply)
              + local_ssd_count   = (known after apply)
              + machine_type      = (known after apply)
              + metadata          = (known after apply)
              + min_cpu_platform  = (known after apply)
              + oauth_scopes      = (known after apply)
              + preemptible       = (known after apply)
              + service_account   = (known after apply)
              + tags              = (known after apply)
              + taint             = (known after apply)

              + shielded_instance_config {
                  + enable_integrity_monitoring = (known after apply)
                  + enable_secure_boot          = (known after apply)
                }

              + workload_metadata_config {
                  + node_metadata = (known after apply)
                }
            }

          + upgrade_settings {
              + max_surge       = (known after apply)
              + max_unavailable = (known after apply)
            }
        }

      + release_channel {
          + channel = (known after apply)
        }
    }

  # google_container_node_pool.default will be created
  + resource "google_container_node_pool" "default" {
      + cluster             = "demo-cluster"
      + id                  = (known after apply)
      + initial_node_count  = (known after apply)
      + instance_group_urls = (known after apply)
      + location            = "europe-west4"
      + max_pods_per_node   = (known after apply)
      + name                = "demo-cluster-node-pool"
      + name_prefix         = (known after apply)
      + node_count          = 1
      + node_locations      = (known after apply)
      + project             = "ilkerispir"
      + version             = (known after apply)

      + management {
          + auto_repair  = (known after apply)
          + auto_upgrade = (known after apply)
        }

      + node_config {
          + disk_size_gb      = (known after apply)
          + disk_type         = (known after apply)
          + guest_accelerator = (known after apply)
          + image_type        = (known after apply)
          + labels            = (known after apply)
          + local_ssd_count   = (known after apply)
          + machine_type      = "n1-standard-1"
          + metadata          = {
              + "disable-legacy-endpoints" = "true"
            }
          + oauth_scopes      = [
              + "https://www.googleapis.com/auth/logging.write",
              + "https://www.googleapis.com/auth/monitoring",
            ]
          + preemptible       = true
          + service_account   = (known after apply)
          + taint             = (known after apply)

          + shielded_instance_config {
              + enable_integrity_monitoring = (known after apply)
              + enable_secure_boot          = (known after apply)
            }

          + workload_metadata_config {
              + node_metadata = (known after apply)
            }
        }

      + upgrade_settings {
          + max_surge       = (known after apply)
          + max_unavailable = (known after apply)
        }
    }

Plan: 2 to add, 0 to change, 0 to destroy.

Do you want to perform these actions?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: yes 

google_container_cluster.default: Creating...
google_container_cluster.default: Still creating... [10s elapsed]
google_container_cluster.default: Still creating... [20s elapsed]
google_container_cluster.default: Still creating... [30s elapsed]
google_container_cluster.default: Still creating... [40s elapsed]
google_container_cluster.default: Still creating... [50s elapsed]
google_container_cluster.default: Still creating... [1m0s elapsed]
google_container_cluster.default: Still creating... [1m10s elapsed]
google_container_cluster.default: Still creating... [1m20s elapsed]
google_container_cluster.default: Still creating... [1m30s elapsed]
google_container_cluster.default: Still creating... [1m40s elapsed]
google_container_cluster.default: Still creating... [1m50s elapsed]
google_container_cluster.default: Still creating... [2m0s elapsed]
google_container_cluster.default: Still creating... [2m10s elapsed]
google_container_cluster.default: Still creating... [2m20s elapsed]
google_container_cluster.default: Still creating... [2m30s elapsed]
google_container_cluster.default: Still creating... [2m40s elapsed]
google_container_cluster.default: Still creating... [2m50s elapsed]
google_container_cluster.default: Still creating... [3m0s elapsed]
google_container_cluster.default: Still creating... [3m10s elapsed]
google_container_cluster.default: Still creating... [3m20s elapsed]
google_container_cluster.default: Still creating... [3m30s elapsed]
google_container_cluster.default: Still creating... [3m40s elapsed]
google_container_cluster.default: Still creating... [3m50s elapsed]
google_container_cluster.default: Still creating... [4m0s elapsed]
google_container_cluster.default: Still creating... [4m10s elapsed]
google_container_cluster.default: Still creating... [4m20s elapsed]
google_container_cluster.default: Still creating... [4m30s elapsed]
google_container_cluster.default: Still creating... [4m40s elapsed]
google_container_cluster.default: Still creating... [4m50s elapsed]
google_container_cluster.default: Still creating... [5m0s elapsed]
google_container_cluster.default: Still creating... [5m10s elapsed]
google_container_cluster.default: Still creating... [5m20s elapsed]
google_container_cluster.default: Still creating... [5m30s elapsed]
google_container_cluster.default: Still creating... [5m40s elapsed]
google_container_cluster.default: Still creating... [5m50s elapsed]
google_container_cluster.default: Creation complete after 5m59s [id=projects/ilkerispir/locations/europe-west4/clusters/demo-cluster]
google_container_node_pool.default: Creating...
google_container_node_pool.default: Still creating... [10s elapsed]
google_container_node_pool.default: Still creating... [20s elapsed]
google_container_node_pool.default: Still creating... [30s elapsed]
google_container_node_pool.default: Still creating... [40s elapsed]
google_container_node_pool.default: Still creating... [50s elapsed]
google_container_node_pool.default: Still creating... [1m0s elapsed]
google_container_node_pool.default: Creation complete after 1m5s [id=projects/ilkerispir/locations/europe-west4/clusters/demo-cluster/nodePools/demo-cluster-node-pool]

Apply complete! Resources: 2 added, 0 changed, 0 destroyed.

Outputs:

endpoint = 34.91.84.154
master_version = 1.16.13-gke.401
```