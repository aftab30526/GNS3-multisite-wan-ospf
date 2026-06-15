================================================================================
                    CCN GNS3 PROJECT — README
================================================================================

Team Name      : [TeamAlpha]
Team Members   : [Aftab Ahmed] — [30526]
                 [M Mustafa] — [31169]
Network Type   : [Multi-Site WAN (OSPF/RIP)]
Submission     : Phase 2 — End of Week 4

--------------------------------------------------------------------------------
1. FOLDER STRUCTURE
--------------------------------------------------------------------------------

TeamName_GNS3_Project/
│
├── README.txt                          ← This file
│
├── project/
│   └── TeamName_CCN_Project.gns3      ← Main GNS3 project file
│
├── configs/
│ Startup config file

--------------------------------------------------------------------------------
2. HOW TO OPEN THE PROJECT IN GNS3
--------------------------------------------------------------------------------

REQUIREMENTS:
  - Ubuntu 22.04 LTS or 24.04 LTS
  - GNS3 version 2.2.x or later
  - Cisco IOS / IOSv router image (same version used during build)
  - Minimum 4 GB RAM allocated to the VM (8 GB recommended)

STEPS TO OPEN:

  Step 1 — Launch GNS3
    Open a terminal and run:
      $ gns3

  Step 2 — Open the Project
    In GNS3 menu: File → Open Project
    Navigate to:  project/Teamalpha_CCN_Project.gns3
    Click Open.

  Step 3 — Verify Router Images
    If GNS3 prompts for missing IOS images, import the same Cisco IOS image
    used during the project build. Go to:
      Edit → Preferences → Dynamips → IOS Routers → Add Image

  Step 4 — Load Startup Configurations (if not auto-loaded)
    Right-click each device → Edit Config → paste content from configs/ folder
    OR place .cfg files in the GNS3 project directory and restart devices.

  Step 5 — Start All Devices
    Click the green "Start All Nodes" button (▶▶) in the toolbar.
    Wait for all devices to fully boot (30–60 seconds).

  Step 6 — Verify Connectivity
    Open console on any router and run:
      Router# show ip route
      Router# show ip interface brief
      Router# ping [destination IP]

--------------------------------------------------------------------------------
3. DEVICE SUMMARY
--------------------------------------------------------------------------------

  Device Name    | Type      | Role                  | Management IP
  ---------------+-----------+-----------------------+------------------
  Router1        | Cisco IOS | Core / Edge Router    | [192.168.1.0/24]
  Router2        | Cisco IOS | Branch Router         | [192.168.2.0/24]
  Router3        | Cisco IOS | WAN Router            | [192.168.3.0/24]
  PC1–PC9        | VPCS      | End Hosts             | [DHCP / Static]



--------------------------------------------------------------------------------
4. SERVICES CONFIGURED
--------------------------------------------------------------------------------

  - DHCP   : Enabled on [Router1 / R2 / R3]
  - NAT    : Configured on [Router1] for internet simulation
  - DNS    : 
  - Routing: [OSPF — Area 0 across all routers]
  - VLANs  : 3

--------------------------------------------------------------------------------
5. NOTES & KNOWN ISSUES
--------------------------------------------------------------------------------

  - All devices must be started before running ping tests.
  - If a device fails to boot, check that the correct IOS image is linked.
  - Serial interfaces (for WAN links) require HDLC or PPP encapsulation —
    this is already set in the startup configs.
  - [Add any other project-specific notes here]

--------------------------------------------------------------------------------
                         END OF README
================================================================================
