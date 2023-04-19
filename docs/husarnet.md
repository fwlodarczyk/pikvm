# Husarnet VPN

[Husarnet](https://husarnet.com/) can be used to access PiKVM on the internal network. This is a convenient and free (for private use) tool for organizing a small or large VPN network. This document is provided as an example for accessing your pikvm using Husarnet. Basic support like whats shown below is provided as an example, any other setting or functionality needs to be redirected to the appropriate community.


## Installation

### On the PiKVM side

1. Use these commands:

    ```
    # Make sure you are logged as root if using web terminal.
    su -
    # now run Husarnet installer for PiKVM
    curl -s https://raw.githubusercontent.com/husarnet/blog-examples/main/pikvm-husarnet/husarnet-pikvm.sh | bash
    ```

2. After success, perform soft reboot using `reboot` command to make sure that everything will work correctly.

3. Join PiKVM to Husarnet network and remount filesystem to read only mode

    ```
    # Make sure you are logged as root if using web terminal.
    su -
    # Add PiKVM to your Husarnet network
    husarnet join fc94:b01d:1803:8dd8:b293:5c7d:7639:932a/XXXXXXXXXXXXXXXXXXXXX PiKVM
    # remember to remount filesystem to read only mode
    ro
    ```

### For each device you wish to access PiKVM

* Install Husarnet using either [Windows]() or [Linux]() installation guide on the system you are using, not to the system you want to control.
* Check the [admin page](https://app.husarnet.com) to view your VPN network.
* Follow the URL in the web browser: `https://[PiKVM_IPv6]` and you will see PiKVM web interface.

??? note
    * BASIC troubleshooting in case this fails in some way: Uninstall Husarnet and install it again.
    
    ```
    # pacman -Rscnd husarnet
    # reboot
    ```
    
    * Follow the above instructions to reinstall
    
