# AppDynamics Analytics Remote Agent to deploy as CloudFoundry App

The Analytics Agent can be used within CloudFoundry 

To deploy the Application to CloudFoundry the [Dist Zip Container](https://github.com/cloudfoundry/java-buildpack/blob/master/docs/container-dist_zip.md) of the [Java Buildpack](https://github.com/cloudfoundry/java-buildpack) is used.

## Prepare
1. Download the Analytics Agent you want to use by
  * by `./get-agent.sh <Portal User> <Agent Version X.X.X.X>` (Will Prompt for Password)
  * by downloading manually and unzipping to this directory
2. [Enable the Analytics Agent as Standalone Binary](https://docs.appdynamics.com/display/PRO42/Installing+Agent-Side+Components#InstallingAgent-SideComponents-EnabletheAnalyticsAgentasStandaloneBinary)
  * Change `conf/analytics-agent.properties`

## Deploy

1. Deploy the Agent to CloudFoundry
  * by `cf push <Analytics Agent Name>`
  * The AppDynamics Application Name will be the `space_name` from `VCAP_APPLICATION` by default
  * The AppDynamics Application Name will be the `application_name` from `VCAP_APPLICATION` by default
  * The AppDynamics Node Name will be `application_name:instance_index` from `VCAP_APPLICATION` by default
  * The AppDynamics Unique Host ID will be `application_name:instance_index` from `VCAP_APPLICATION` by default

## Clean

1. Use `./clean.sh` to delete the Agent files
