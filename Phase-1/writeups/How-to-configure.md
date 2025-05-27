# Environment Setup

In this project, I have set up a virtual environment with two systems:

- **Win11 (Wazuh Agent)**
- **Debian (Wazuh Manager)**

## Wazuh Manager Setup

The easiest way to set up the Wazuh Manager is by using the official installation script provided on their website. Here's how to do it:

1. **Install Wazuh Manager:**
   - Navigate to the [Wazuh website](https://wazuh.com/) and follow their "Easy Installation" script. This script will handle most of the setup for you, making it quick and straightforward.

2. **Access Wazuh Dashboard:**
   - Once the installation is complete, access the Wazuh dashboard using the provided URL.

3. **Add an Agent:**
   - In the Wazuh dashboard, go to the "Agents" section and add an agent. For this setup, I've added **Win11** as the agent.

## Wazuh Agent Setup (Win11)

1. **Install Sysmon on the Agent (Win11):**
   - First, download **Sysmon** from Microsoft's Sysinternals suite.
   - Next, configure Sysmon using the configuration file from [SwiftOnSecurity]. This will set up Sysmon to collect and log various system events for monitoring.

2. **Configure Wazuh Agent:**
   - On the **Win11** agent, modify the `ossec.conf` file to specify the location of the Sysmon logs. This ensures that Wazuh can correctly collect and forward the logs from Sysmon to the Wazuh Manager.

## Testing

Try to login to windows (agent) using wrong passwords. They will show up in Wazuh dashboard. (Hint, try to find rule.id 80122)
