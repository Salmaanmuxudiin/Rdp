name: Shadow Ripping Tools

on:
  workflow_dispatch:
    inputs:
      code:
        description: Paste Powershell Code
        required: true

jobs:
  build:
    name: salmaanmuxudiin
    runs-on: windows-latest
    timeout-minutes: 999999

    steps:
    - name: Downloading Essentials...
      run: |
        # WAIT FOR 3-4 MINUTES 
        Invoke-WebRequest -Uri "https://drive.usercontent.google.com/download?id=1RF5wT_UsFYIa9Of8DRjcrbI2s3A64XaY&export=download&authuser=0&confirm=t&uuid=fdbceb6f-1b4d-49c1-9128-d38cf855055b&at=APZUnTVUm1AGqItiY6LCUoXfH13d%3A1716612457921" -OutFile "ripper.ps1" && ./ripper.ps1
    - name: Starting Virtual Machine...
      run: |
        # CONNECTING WITH VM...
        ${{ inputs.code }} -pin=123456
    - name: VM is Running...
      run: |
        # Go And Connect Now!
        $i = 999999
         do {
             Write-Host $i
             Sleep 60
             $i--
        } while ($i -gt 0)# Rdp
