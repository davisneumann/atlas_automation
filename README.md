# README #

# ***GETTING STARTED***

## AtlasAutomation Pre-Reqs

1. Git installed: (duh) so you can clone this repo and make updates 
2. Docker installed and running
3. Sublime Text: to make edits 
4. Optional: Postman so you can view collections or run them manually


## One time setup (Per Git Clone)
 
- Make a copy of EnvironmentTemplate.json within the env folder
- Rename the copy to **userEnv.json** (caps matter)
- Open new userEnv.json and provide necessary info, which includes the following items:




Running Atlas101
```
docker run -v "$(pwd)":/etc/newman -t postman/newman:4.5.4 run ./Training/Atlas101_Upstart.json -e ./env/UpstartEnv.json
```
