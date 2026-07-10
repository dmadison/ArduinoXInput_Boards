# How to Update the Package Manifest

### 1. [Install Python 3](https://www.python.org/downloads/)

### 2. Install required module dependencies

```
python -m pip install -r adafruit-bpt/requirements.txt
```

### 3. Check for updates

Run the Adafruit Arduino Board Package Tool (bpt) script from the repository's home directory, using the `bpt.ini` config file, the `package_dmadison_xinput_index.json` board index JSON file, and the `check-updates` command:

```
python adafruit-bpt/bpt.py -c adafruit-bpt/bpt.ini -i package_dmadison_xinput_index.json check-updates
```

This will poll the XInput board GitHub repositories for updates:
```
Comparing current packages with published versions in board index...
- XInput AVR Boards
    latest index version = 1.0.5
    !!!! BOARD INDEX NOT UP TO DATE !!!!
- XInput SparkFun Boards
    latest index version = 1.0.0
```

### 4. Update the board index

If the board index is not up to date, run the script again with the `update-index` command. There are two packages in the repo: "XInput AVR Boards", and "XInput SparkFun Boards". Each package needs to be updated separately:

```
python adafruit-bpt/bpt.py -c adafruit-bpt/bpt.ini -i package_dmadison_xinput_index.json update-index "XInput AVR Boards"
python adafruit-bpt/bpt.py -c adafruit-bpt/bpt.ini -i package_dmadison_xinput_index.json update-index "XInput SparkFun Boards"
```

If the remote contains a newer version of the boards, the script will create a new board package archive (tarball) and update the board index JSON.

### 5. Commit the changes

And we're done :D
