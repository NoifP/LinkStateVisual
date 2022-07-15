# Graphing OSPF in OSPF

## Collect Data

1. Login to any router that is participating in your OSPF network.
1. Make sure you are logging to file because it'll probably exceed your terminal screen buffer!
1. Use something like one of the following commands to extract OSPF data:

   * OSPF:

      ```cisco
      term len 0
      show ip ospf database router
      ```

   * OSPF instance 3:

      ```cisco
      term len 0
      show ip ospf 3 database router
      ```

   * OSPF v3 Internet VRF:

      ```cisco
      term len 0
      show ospfv3 vrf Internet database router
      ```

1. Save the results to a file named something like `ospf-2021-09-30.txt` in the LinkStateVisual folder.

## Transform Data

1. In linux load up the python environment by going into LinkStateVisual folder and then running `source ./bin/activate`.
1. Run LinkStateVisual... `lsv2.py ospf-2021-09-30.txt` and it should produce a `.dot` and a `.gexf` file for you.

## Load Data into Gephi

1. Open up Gephi and import the `.gexf` file.
1. In Data Laboratory filter and delete any nodes that you don't want to graph (depending on your use case):
1. If you need nodes labelled with hostnames (for example) you can do that in the Data Laboratory by editing the label. Circles / double circles are routers. Rectangles are links/prefixes.
1. Tinker until it looks good in Gephi and render it out!
    * `Yifan Hu Proportional` seems to work ok for layout.
