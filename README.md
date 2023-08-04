<h1 align="center">
Dataset generation
</h1>

**Step 1:** On the https://www.tpc.org/ website, go to the Downloads tab and select the appropriate tools for TPC-DS to download (.zip). Fill out the form and after receiving them by email, download and unpack them onto your computer.  

**Step 2:** Install Visual Studio, making sure to select the Desktop development with C++ and Linux and embedded development with C++ toolsets - the rest is up to you.  

![](https://file.notion.so/f/s/5c6f231b-5fc7-4abe-ab2e-d6f74a0610ab/Untitled.png?id=6a10220d-675e-4013-9f70-07c28bbaf3b2&table=block&spaceId=4c5155b1-421a-41d9-85a1-d2ba99304c21&expirationTimestamp=1691236800000&signature=OJs-ve8plY1wJzWjIDok6v_HDHt1Q5tb29ardL1lEJY&downloadName=Untitled.png)  

**Step 3:** In the unpacked folder, navigate to the tools folder and find the file named dbgen2.sln. Open it in Visual Studio (you may see an error message saying that the "project file grammar.vcproj" has failed to load - you can safely ignore this error). You should see the following message regarding project upgrades (without upgrades, projects will have an incompatible status). Select OK.  

**Step 4:** From the list of projects (on the right side in the Solution Explorer window), right-click on dsdgen and select "Build", or select the project (click once with the left mouse button) and choose Build → Build Solution from the toolbar.  

**Step 5:** Create a new folder called "tmp" where generated data will appear: 
```bash
mkdir tmp
```

**Step 6:** Run data generation (scale 100 means 100 GB): 
```bash
./dsdgen.exe /dir tmp /scale 100
```

**Step 7:** The generated data is in .dat format and contains an unnecessary, empty column, which may be an obstacle to loading the data into tools later on. If you want to convert it to csv format and remove the unnecessary column, you can use the `convert_dat_to_csv.py` script.
