---
tags:
  - electrical-engineering
  - electrical-design
  - sbm
---
# Steps
## 1. Import CAD
Take the site plan .dwg file and import it into AGI. Ensure to change the "Units Specified in CAD File" from metres to the unit in the file (either millimetres or feet). Check the box "Flatten Drawing Entities." Click OK.
## 2. Save the .AGI file
Save the .AGI file under
`Project Name` > `04 dDocs` > `08 Elec` > `04 - Lighting` > `02 - Exterior` > `02 - Photometric Calcs`[^1]
## 3. Trace outline of buildings / walls
Select the `Rooms/Objects` tab under the Model Toolkit (typically on the right hand side). Select the 3rd icon from the left next to `Add Object` (<img class="icon" src="agi-polygon-object.png" />). This will create an object that follows a user-defined polygon. In the dialog that opens enter a fitting name for the object, select its colour, and make sure to adjust the `Height of Sides` entry to the height of the building / wall you are modeling. For exterior photometrics, leave the values under `Surfaces` as $0.5$.

>[!tip] Removing or editing an object
> If you make a mistake when drawing an object, select the <img class="icon" src="agi-delete-object.png" /> icon and then `Right Click` to delete the object or the <img class="icon" src="agi-edit-object.png" /> icon to edit it. 

Trace out the outline of the buildings. Refer to Architectural or Civil drawings to better see the building outline. Be careful not to include any canopies. When you get to the last vertex, right click to close the polyline. When complete, you can use `Shift` + `Middle Mouse` to orbit and check the heights of objects.

>[!tip] Redo previous command
>You can use `Right Click` to redo the last command you entered. This is useful for sites where there are multiple distinct buildings, like a subdivision.
## 4. Add canopies (if applicable)
If the building has overhangs or canopies, we add them similar to how we add buildings. Click one of the tools beside `Add Object`, name and colour it, and give it its height. Once you close the dialog box, however, look at the bottom right corner of the window. There will be a yellow circle with a black exclamation mark that says `Z-Coord Object` beside it. Change this value to the height of the underside of the canopy you are adding.
## 5. Insert calculation points
In the Model Toolkit, select the `Calculations` tab. Next to `Add:`, select the calculation points grid icon <img class="icon" src="agi-calc-grid.png" /> . In the dialog that opens, give the grid a label. Ensure the spacing is 10' x 10' between points. None of the other options should need to be changed. Click OK.  If this is an exterior plan, draw a grid that is large enough to cover the entire site as well as its perimeter.

Exterior plans will also need calculation points to be removed from within buildings. To do this, select the drop down on the <img class="icon" src="agi-remove-calc-building.png" /> icon. Select `Within Entities` > `Single`. Then select all buildings (not canopies). Once you've selected them all, press `Right Click`. All the calculation points within those buildings should now be removed.
## 6. Create statistical areas
Now that we have a grid of calculation points, we need to divide these points into different zones (e.g. Parking, Drives, etc.). In the same `Calculations` tab, select the <img class="icon" src="agi-stat-area-create.png" /> icon to create a statistical area. In the dialog, give this area a meaningful name and a colour that will stand out from other objects / areas.
## 7. Get .ies files
The .AGI file is prepped. Now we need to get .ies files. These model numbers will normally be provided (or at the very least similar fixtures from previous projects will be provided). Once you have located the .ies files, save them to the `02 - Photometric Calcs` > `ies Files` directory.

To add them into AGI, select the `Luminaire` tab in the Model Toolkit. Select the <img class="icon" src="agi-define.png" /> button. This will open a window. In the top left, select `Browse/Recent` and navigate to the folder that the .ies files are located. When you select them, another dialog box will open. This is where you will set the fixture's mounting type.[^2] Once you've selected the appropriate mounting click OK. Give the fixture a tag and change the wireframe colour. **Change the LLF to $0.85$**. Click the Ok button with the green checkmark in the top right corner.
## 8. Place fixtures
The current fixture you have selected is shown in the drop down text box beside `Label`. Click the drop down to change fixtures. Below that is a box named `MH` (Mounting Height). Change this value to whatever height the fixture is being mounted at (in feet). Then click the <img class="icon" src="agi-locate-orient.png" /> button to place the fixture. `Left Click` once to place it, then move the cursor to aim the fixture. `Left Click` a second time to lock in its orientation.

>[!tip] Spacing poles
>Pole mounted lights on site photometrics need to be $1.5\ \mathrm{m}$ from any buried service (i.e. sewage, water supply, etc.)
## 9. Calculate illuminance
Once fixtures have been placed, hit the <img class="icon" src="agi-calculate.png" /> button.[^3] This will change all the calculation points from question marks to actual [[Illuminance|illuminance]] values, measured in [[Foot-candle|foot-candles]]. Refer to the [[#Typical values|typical values table]] below to see what levels you should be expecting for various different areas. If areas are not as illuminated as expected, move fixtures or change fixture types until desired illuminance is desired.
## 10. Export to CAD
Once the photometric is complete we need to export it to AutoCAD. To do this, click the <img class="icon" src="agi-export.png" /> button at the top. In the window that opens up, be sure to select the correct units beside `Units Will Be Converted To`. Under `Export Types`, be sure that *at least* `Luminaires`, `Calc Points`, and `Drawing` are checked.[^4]
# Typical values
| Area                      | Avg Illuminance ($\mathrm{fc}$) |
| ------------------------- | ------------------------------- |
| Drives                    | $2.0$                           |
| General Parking           | $2.0$                           |
| Barrier Free Parking      | $3.0 - 5.0$                     |
| Bike Storage              | $2.0$                           |
| Sidewalks / Walk lanes    | $1.0$                           |
| Entrances                 | $5.0 - 10.0$                    |
| Outside of property lines | $0.0$                           |

[^1]: Its rare but if you are working on an interior photometric the path is the same except replace the `02 - Exterior` block with `01 - Interior`.

[^2]: For pole mounted fixtures with an arm, set the `Arm Length` to $0.5$

[^3]: If doing a rough calculation you can select `Direct Only Method` from the drop down, but final calculations must be done with the `Full Radiosity Method`.

[^4]: `Templates` will bring the 'bubble' that surrounds fixtures, and `Statistical Areas` can be useful to show the different zones used in CAD.
