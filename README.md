# iotkit-agent

Edge agent to abstract cloud connectivity complexities. It allows edge developers to focus on writing their experiments and interacting with I/O parameters. When sending data to the cloud, the message formatting and security is implemented in the agent so only the message payload has to be provided.   

![Agent Topology](../master/images/agent-topo.png?raw=true)

## Deployment

> This portion of the read me is only required for the initial deployment of the `iotkit-agent`. In many the SD card provided with your board will already come configured with this agent, in which case you can move on to the Usage portion of this read me.

### Installation

In the iotkit-agent directory run:

    npm install
    
### Configuration

The `iotkit-agent`, by default, requires only two arguments: IoT Kit username and password. There are three ways you can define these information:

* Hard-coded in to the `start-agent.sh` script
* Configuration file (cloud.json) in root of the application
* Environment variables 


#### Hardcoded 

Edit `start-agent.sh` script:

    export BROKER_HOST_USR="example-user"
    export BROKER_HOST_PSW="example-password"

> Not ideal, as this file will be overwritten when applicant is updated.

#### Configuration File

Drop configuration file in the root of the `iotkit-agent` application:

    {
      username: 'testuser',
      password: 'password'
    }
    
> The configuration file must be named `cloud.json` and include valid JSON in the above format. 

#### Environment Variables 

Define two arguments as environment variables and the `iotkit-agent` will automatically use them:

    export IOTKIT_AGENT_USR="example-user"
    export IOTKIT_AGENT_PSW="example-password"
    
> Just remember to either source the file where you defined these values or just restart your console to make sure `iotkit-agent` will see these values.
    
### Start

To start the agent service simply execute the `start-agent.sh` file:

    ./start-agent.sh
    
### Stop

    ./stop-agent.sh

## Usage

For instructions how to use the `iotkit-agent` please the [iotkit-samples repo](https://github.com/enableiot/iotkit-samples).