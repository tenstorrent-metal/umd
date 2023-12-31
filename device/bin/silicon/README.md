The files in this folder are generated by running "make customer-release" in src/t6ifc/t6py (from the t6py venv).

*reset.sh* can be used to toggle the reset signal on the board (provided that the board has the reset dongle attached). This must be run on host OS, and not inside a Docker container.
Use lsusb to check for reset dongle; you should see something like:
```
Bus 001 Device 002: ID 0403:6014 Future Technology Devices International, Ltd FT232H Single HS USB-UART/FIFO IC
```

*tt-script* is a usefull tool to run python scripts. For example, run *tt-script status* to see the status of your board.

*clkctl* allows the aiclk to be manually set and all of the clocks to be listed
  - `clkctl list` displays the current values of the clocks
  - `clkctl force --aiclk <value>` forces the aiclk to the specified value
      - this may fail if the value is greater or less than safe values
  - `clkctl unforce` reverts the board back to default production aiclk behaviour
