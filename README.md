## Pipeline for deploying Prometheus to PCF

This pipeline sets up a Prometheus monitoring environment for PCF.

It can target an ops manager BOSH director or a standalone one.

## Jobs

- **Upload Release**

  Uploads the Prometheus and Routing BOSH releases to the target director.

- **Create UAA Creds**

  Creates UAA Credentials both in Cloud Foundry and BOSH (requires Ops Manager for now)

- **Deploy**

  Performs the deployment

## Parameters:


  - `github_token`: A github token
  - `pcf_sys_domain`: PCF System Domain
  - `prometheus_secret`: Secret for the prometheus UAA client
  - `deploy_azs`: Deployment AZs (Array)
  - `deploy_network`: Deployment Network
  - `deploy_vm_password`: SHA of the VM Password
  - `deploy_nginx_ip`: IP for front end server
  - `bosh_creds_source`: Source of BOSH credentials (`opsman` or `manual`)

If you are using ops manager
  - `pcf_opsman_admin_username`: Ops Manager admin username
  - `pcf_opsman_admin_password`: Ops Manager admin password
  - `opsman_url`: Ops Manager URL
  - `pcf_ert_domain`: Main CF Domain

If you are providing credentials manually:

 - `bosh_username`: BOSH Director username
 - `bosh_password`: BOSH Director password
 -  `director_ip`: BOSH Director IP
 - `bosh_ca`: BOSH CA certificate (if any)
 - `nats_machines`: NATS Machines
 - `nats_username`: NATS Username
 - `nats_password`: NATS Password
