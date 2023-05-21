Install IPFS-CLI
=======================

Pre-requisites
1.  Install Go-lang
2.  Set the Go path

## Install the IPFS-Go commandline tool

1.  Search for ipfs in google.com
2.  #### Click on the link 
        https://ipfs.tech
3.  Click on the Install tab
4.  The tab re-directs to the installation options
5.  Click on Commandline install "Install the IPFS CLI" button
6.  The button link re-directs to "Initialize a Kubo node and interact with the IPFS Network"
7.  Scroll down to Prerequisites
8.  Click the "Kubo install guide"
9.  The link loads the "Install IPFS Kubo"
10. #### Choose the desired OS to download the Go-IPFS. For MAC Silicon, run the following to download
        curl -O https://dist.ipfs.tech/kubo/v0.20.0/kubo_v0.20.0_darwin-arm64.tar.gz
11. #### After download, unizp the file
        tar -xvzf kubo_v0.20.0_darwin-arm64.tar.gz
12. #### Once unzipped, the "kubo" folder appears
        kubo/
        kubo/ipfs
        kubo/install.sh
13. #### Navigate to the kubo directory
        cd kubo
14. #### Run the install script:
        sudo bash install.sh
15. #### On successful install, the following displays
        Moved ./ipfs to /usr/local/bin
16. #### Confirm Kubo installation:
        ipfs --version
17. #### If Kubo is installed, the version number appears
        ipfs version 0.20.0
18. #### Initialize IPFS. Open a new terminal window
        ipfs init
21. #### The output displays a peer identity
        peer identity: 12D3KooWJMVPyoy3xWTPJbEFA9KrWUVd5hLzYGZepU1vift4CV6y
22. #### Start the IPFS Daemon 
        ipfs daemon
23. #### The output displays 
        Gateway server listening on /ip4/127.0.0.1/tcp/8080
        Daemon is ready
22. Note the port on which the gateway server is running
23. Switch back to the original terminal window
24. #### Run "ipfs swarm peers" to see the IPFS addresses of your peers:
        ipfs swarm peers
25. #### The output displays a list of peer addresses
        /ip4/116.202.229.43/udp/44788/quic/p2p/12D3KooWLtc9wTNZrnqmpmDvVz1XC48zWk4kuFAkr3e7835o9H4b
        /ip4/157.245.90.53/tcp/4001/p2p/QmZqRijAimAmCUjDdSw1bTQFw6BAAxzpLRXKUouMnSdp2g
        /ip4/207.246.102.156/udp/4001/quic/p2p/12D3KooWParrKq9KMZxe4hhKhqhNyz4dmnsR8xridAwa6Y1MLQtj
        /ip4/34.67.84.45/tcp/4001/p2p/12D3KooWAZtghTGzhZ7aZhYi2fQnY1eRZRTDpgfgFJmuacCreoGX
        /ip4/87.117.121.163/tcp/4001/p2p/12D3KooWDEN5aRpdi6KCyP4A9ZP4z7TtyGymkAgG2PNNgBgpm4nQ
26. #### Now, fetch a cool picture of a spaceship launch from the network using ipfs cat:
        ipfs cat /ipfs/QmSgvgwxZGaBLqkGyWemEDqikCqU52XxsYLKtdy3vGZ8uq > ~/Desktop/spaceship-launch.jpg
27. The command above fetches a picture named "spaceship-launch.jpg"
28. The command fetches the picture and stores it in ~/Desktop folder
29. #### Next create a file to add to our node.
        echo "meow" > meow.txt
30. #### Add meow.txt using ipfs add:
        ipfs add meow.txt
31. #### The output displays below:
        added QmabZ1pL9npKXJg8JGdMwQMJo2NCVy9yDVYjhiHK4LTJQH meow.txt 5 B / 5 B [===========================================================================]

32. Note the CID above as it will be needed later
33. #### Now view the file just created using curl
        curl "https://ipfs.io/ipfs/QmabZ1pL9npKXJg8JGdMwQMJo2NCVy9yDVYjhiHK4LTJQH"
34. #### Output like the following displays:
        meow
35. #### View the objects on your the local gateway:
        curl "http://127.0.0.1:8080/ipfs/QmabZ1pL9npKXJg8JGdMwQMJo2NCVy9yDVYjhiHK4LTJQH"
36. #### Output like the following displays:
        meow
37. #### View the object on the web browser
        https://ipfs.io/ipfs/QmabZ1pL9npKXJg8JGdMwQMJo2NCVy9yDVYjhiHK4LTJQH


## WEB Console

38. #### Interact with the node using the web console
        localhost:5001/webui
39. The web console shows files that are in your Mutable File System (MFS)
    
    When files are added using the CLI command "ipfs add ...", these files are not automatically available within the MFS. 
    
    To view files in IPFS Desktop that are added using the CLI, the files must be copied over to the MFS:
40. #### Enter localhost:5001/webui into your browser to view the web console.
        localhost:5001/webui
41. In the left sidebar menu, click Files. An empty directory displays, along with the following message:
    -   No files here yet! Add files to your local IPFS node by clicking the Import button above.
42. Navigate back to your original terminal window.
43. #### Using the CID <CID> obtained when adding meow.txt to the local node in the previous step, copy the files over to the MFS.
        ipfs files cp /ipfs/QmabZ1pL9npKXJg8JGdMwQMJo2NCVy9yDVYjhiHK4LTJQH /meow.txt
44. Refresh the web console again
45. The "meow.txt" file can now be seen.


## Install IPFS-Desktop

1.  Navigate to ipfs.io/#install
2.  Scroll down to IPFS Desktop
3.  #### Click the "Install IPFS Desktop" button to load the IPFS Desktop page
        https://docs.ipfs.tech/install/ipfs-desktop/
4.  It loads the page IPFS Desktop page
5.  Scroll down to the OS (mac)
6.  #### Click on the github OS download page below
        https://github.com/ipfs/ipfs-desktop/releases
6.  Scroll down to Assets
7.  #### Click on the mac download link
        https://github.com/ipfs/ipfs-desktop/releases/download/v0.28.0/ipfs-desktop-0.28.0-mac.dmg
8.  Once downloaded, open the "ipfs-desktop.dmg" file
9.  Drag the IPFS icon to the Applications folder
10. Open the Applications folder and open the IPFS Desktop application
11. A warning might appear: IPFS Desktop.app can't be opened. Click Show in Finder:
12. Find IPFS Desktop.app in the Applications folder
13. Hold down the control key, click IPFS Desktop.app, and click Open:
14. Click "Open", in the new window:
15. IPFS icon can now be seen in the status bar:
16. The IPFS Desktop application has finished installing. Now, add local site.


## IPFS Companion

1.  #### Use the link below to go to the IPFS Companion page
        https://docs.ipfs.tech/install/ipfs-companion/#prerequisites
