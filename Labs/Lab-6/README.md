# Lab-6: Four-Router Network

## Objective
Learn advanced networking concepts by setting up a network with four routers and seven distinct networks in Cisco Packet Tracer.

## Lab Topology
![Lab-6](Lab-6.png) 

## Equipment
- 8 PCs
- 4 Switches
- 4 Routers

## Configuration

### Network Configuration

| Sl. No. | Equipment Title              | Label | IP Address    | Subnet Mask       | Gateway IP Address |
|---------|------------------------------|-------|---------------|-------------------|---------------------|
| 1       | Desktop Computer             | PC0   | 1.1.1.2       | 255.0.0.0         | 1.1.1.1             |
|         |                              | PC1   | 1.1.1.3       | 255.0.0.0         | 1.1.1.1             |
|         |                              | PC2   | 2.2.2.2       | 255.0.0.0         | 2.2.2.1             |
|         |                              | PC3   | 2.2.2.3       | 255.0.0.0         | 2.2.2.1             |
|         |                              | PC4   | 3.3.3.2       | 255.0.0.0         | 3.3.3.1             |
|         |                              | PC5   | 3.3.3.3       | 255.0.0.0         | 3.3.3.1             |
|         |                              | PC6   | 4.4.4.2       | 255.0.0.0         | 4.4.4.1             |
|         |                              | PC7   | 4.4.4.3       | 255.0.0.0         | 4.4.4.1             |
| 2       | Switch                       | 1     |               |                   |                     |
| 3       | Switch                       | 2     |               |                   |                     |
| 4       | Switch                       | 3     |               |                   |                     |
| 5       | Switch                       | 4     |               |                   |                     |
| 6       | Router0                      | Fa0/0 | 1.1.1.1       | 255.0.0.0         |                     |
|         |                              | Fa0/1 | 10.10.10.1    | 255.0.0.0         |                     |
| 7       | Router1                      | Fa0/0 | 2.2.2.1       | 255.0.0.0         |                     |
|         |                              | Fa0/1 | 10.10.10.2    | 255.0.0.0         |                     |
|         |                              | Fa0/2 | 20.20.20.1    | 255.0.0.0         |                     |
| 8       | Router2                      | Fa0/0 | 3.3.3.1       | 255.0.0.0         |                     |
|         |                              | Fa0/1 | 20.20.20.2    | 255.0.0.0         |                     |
|         |                              | Fa0/2 | 30.30.30.1    | 255.0.0.0         |                     |
| 9       | Router3                      | Fa0/0 | 4.4.4.1       | 255.0.0.0         |                     |
|         |                              | Fa0/1 | 30.30.30.2    | 255.0.0.0         |                     |

### Routing Table Configuration

1. **Access Router GUI:**
   - Click on Router.
   - Go to the `Config` -> `Routing` -> `Static`.
   - Enter the network, subnet mask and next hop as shown in the table below.

| Router Name | Destination Network  | Subnet Mask   | Next Hop    |
|-------------|----------------------|---------------|-------------|
| R0          | 2.0.0.0              | 255.0.0.0     | 10.10.10.2  |
|             | 3.0.0.0              | 255.0.0.0     | 10.10.10.2  |
|             | 4.0.0.0              | 255.0.0.0     | 10.10.10.2  |
| R1          | 1.0.0.0              | 255.0.0.0     | 10.10.10.1  |
|             | 3.0.0.0              | 255.0.0.0     | 20.20.20.2  |
|             | 4.0.0.0              | 255.0.0.0     | 20.20.20.2  |
| R2          | 1.0.0.0              | 255.0.0.0     | 20.20.20.1  |
|             | 2.0.0.0              | 255.0.0.0     | 20.20.20.1  |
|             | 4.0.0.0              | 255.0.0.0     | 30.30.30.2  |
| R3          | 1.0.0.0              | 255.0.0.0     | 30.30.30.1  |
|             | 2.0.0.0              | 255.0.0.0     | 30.30.30.1  |
|             | 3.0.0.0              | 255.0.0.0     | 30.30.30.1  |

2. **Apply Configuration:**
   - Click `Add` to add the routes.
   - Save the configuration.

## Steps

1. **Open Cisco Packet Tracer.**

2. **Add Devices:**
   - Drag and drop 8 PCs, 4 Switches, and 4 Routers onto the workspace.

3. **Connect Devices:**
   - Connect devices as shown in the topology using copper straight-through cables.

4. **Assign IP Addresses:**
   - Configure IP addresses and gateway settings on each PC and routing table on each router as listed in the configuration table above.

5. **Verify Connectivity:**
   - **Using Command Prompt:**
     - Open the `Command Prompt` on each PC.
     - Use the `ping` command to test connectivity between PCs in different networks. For example:
       - From PC0, ping PC2: `ping 2.2.2.2`
       - From PC6, ping PC0: `ping 1.1.1.2`
     - Check for successful replies to confirm connectivity.
     
   - **Using Message PDU Tool:**
     - Click the `Message` PDU tool.
     - Select the source and destination PCs.
     - Check the results in the panel below:
       - **Successful:** If the packets are successfully transmitted between PCs.
       - **Failed:** If the packets are not transmitted, indicating a connectivity issue.

## Conclusion
You have successfully set up a four-router network with seven different networks and configured static routing in Cisco Packet Tracer. 
This lab helps you understand complex IP configuration, inter-router communication and advanced routing setup.
