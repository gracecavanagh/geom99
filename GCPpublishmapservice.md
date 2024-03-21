Date: March 18, 2024 | Time Duration: 5:30pm to 7:30pm | Total Time: 2 hours.

Publishing a map service into ArcGIS Server on GCP VM (part of Week 7 & 8 checklist)
1.	Open ArcGIS Pro->Insert->Connections->Server->New ArcGIS Server
   <img width="263" alt="Screenshot 2024-03-18 173439" src="https://github.com/gracecavanagh/geom99/assets/151089198/b625ddea-837c-4c01-b299-edaf6e269043">
   
2.	Add your IP address /arcgis as the Server URL, and username and the password given in the checklist. Press OK and ignore the certificate pop-up.

<img width="277" alt="Screenshot 2024-03-15 170804" src="https://github.com/gracecavanagh/geom99/assets/151089198/384bde66-5157-4636-8190-87d26d6dcce9">

3. Make sure your VM is up and running, and that the same data you're about to publish is already located on the VM (and you know the file path).
4. Right click Servers in the catalog pane, then Publish->Map Service.
<img width="480" alt="Screenshot 2024-03-18 173505" src="https://github.com/gracecavanagh/geom99/assets/151089198/eb528539-a361-4006-abff-2d551a5309ac">

5. Fill out the information and press Analyze. Resolve warnings and errors by right-clicking them.
<img width="625" alt="Screenshot 2024-03-18 180233" src="https://github.com/gracecavanagh/geom99/assets/151089198/af21bba7-6fb1-4f5b-b983-84ace7c7ff52">

7. The one that says the folder isn't registered needs to be solved by selecting the path to the data located on the server, whether it is using the same path as on your local PC or a different one. Then press Create.
8. Once all of the warnings and errors have been fixed (press analyze again) press Publish.
9. JS View: <img width="850" alt="Screenshot 2024-03-18 192542" src="https://github.com/gracecavanagh/geom99/assets/151089198/37365f35-0cb1-485f-bcc4-a02b4148ee95">

10. Server Manager View: <img width="537" alt="Screenshot 2024-03-18 192454" src="https://github.com/gracecavanagh/geom99/assets/151089198/2560ad9c-88a4-4dae-a673-eb32716a1373">
