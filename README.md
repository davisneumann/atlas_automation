# README #

# ***GETTING STARTED***

## AtlasAutomation Pre-Reqs

1. Git installed: (duh) so you can clone this repo and make updates 
2. Docker installed and running
3. Text Editor (i.e. Sublime Text) to make edits 
4. Optional: Postman so you can view collections or run them manually


## One time setup (Per Git Clone)
 
- Make a copy of EnvironmentTemplate.json within the env folder
- Rename the copy to **UpstartEnv.json** (caps matter)
- Open new UpstartEnv.json and provide necessary info (API keys, client id, secret, credential)


**Offboarding Scripts**

Running OneLogin Removal
```
docker run -v "$(pwd)":/etc/newman -t postman/newman:4.5.4 run ./Entitlements/Atlas_OneLogin_Removal.json -e ./env/UpstartEnv.json

```

Running Lessonly Removal
```
docker run -v "$(pwd)":/etc/newman -t postman/newman:4.5.4 run ./Entitlements/Atlas_Lessonly_Archival.json -e ./env/UpstartEnv.json

```

Running Everbridge Removal
```
docker run -v "$(pwd)":/etc/newman -t postman/newman:4.5.4 run ./Entitlements/Atlas_Everbridge_Removal.json -e ./env/UpstartEnv.json

```

If you want to chain all three together

```
docker run -v "$(pwd)":/etc/newman -t postman/newman:4.5.4 run ./Entitlements/Atlas_OneLogin_Removal.json -e ./env/UpstartEnv.json
docker run -v "$(pwd)":/etc/newman -t postman/newman:4.5.4 run ./Entitlements/Atlas_Lessonly_Archival.json -e ./env/UpstartEnv.json
docker run -v "$(pwd)":/etc/newman -t postman/newman:4.5.4 run ./Entitlements/Atlas_Everbridge_Removal.json -e ./env/UpstartEnv.json

```


**Atlas Scripts - Assigns Atlas Tickets**


Running Atlas101
```
docker run -v "$(pwd)":/etc/newman -t postman/newman:4.5.4 run ./Training/Atlas101.json -e ./env/UpstartEnv.json

```