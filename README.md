# etcd Steps

These steps are great for interacting with the key-value store in [etcd](https://etcd.io/).

---------

<kbd>
  <img src="https://github.com/xmatters/xMatters-Labs/raw/master/media/disclaimer.png">
</kbd>

---------

# Files

* [etcdSteps.zip](etcdSteps.zip) - Workflow zip file with the step and example flow
* [etcd.png](/etcd.png) - etcd logo

# How it works
These steps can communicate with the key-value store in [etcd](https://etcd.io/).


# Installation

## etcd Setup
None required.

Optionally, install the [xMatters Agent](https://help.xmatters.com/ondemand/xmodwelcome/xmattersagent/install-xmatters-agent.htm) on a computer with access to your etcd store for improved security.


## xMatters Setup
1. Download the [etcdSteps.zip](etcdSteps.zip) file onto your local computer
2. Navigate to the Workflows tab of your xMatters instance
3. Click Import, and select the zip file you just downloaded
4. Add an endpoint for etcd. The default port is `2379`, so we used `http://localhost:2379` when using the xMatters Agent.


## Usage
The **etcd - Put KV** and **etcd - Get Range KV** steps is now available in your custom steps. So navigate to the appropriate canvas so you can add the step there. If you'd like to experiment with it, the **Access KV** workflow has a canvas that can be triggered via HTTP call. 

There are 2 steps included:

1. **etcd - Put KV** - This step calls the `/v3/kv/put` HTTP api endpoint.
2. **etcd - Get Range KV** - This step calls the `/v3/kv/range` HTTP api endpoint.

### etcd - Put KV
---
### Inputs
| Name  | Required? | Min | Max | Help Text | Default Value | Multiline |
| ----- | ----------| --- | --- | --------- | ------------- | --------- |
| Key | Yes | 0 | 2000 | Key to set in etcd. | | No |
| Value | Yes | 0 | 2000 | Value to set in etcd. | | No |


### Outputs

| Name | Description |
| ---- | ----------  |
| json | Raw json output from api call |


### etcd - Get Range KV
---
### Inputs
| Name  | Required? | Min | Max | Help Text | Default Value | Multiline |
| ----- | ----------| --- | --- | --------- | ------------- | --------- |
| Key | Yes | 0 | 2000 | Key to set in etcd. | | No |
| Range End | No | 0 | 2000 | Leave blank if you would just like one output key. End of range for keys to get. | | No |


### Outputs

| Name | Description |
| ---- | ----------  |
| json | Raw json output from api call |
| value | Value of key that was requested. Only included if count is 1. |
| count | Number of keys received. |


## Example
This an image of the included flow with the **etcd - Put KV** and **etcd - Get Range KV** steps.

<kbd>
	<img src="/media/ExampleFlow.png">
</kbd>

