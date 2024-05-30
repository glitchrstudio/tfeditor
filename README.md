# TF Editor - Custom song editor for Taiko Frenzy

TF Editor is the official tool for creating and editing custom songs for the VR game [Taiko Frenzy](https://taikofrenzy.glitchr-studio.com).\
With the editor, you can import an audio file in **.wav** or **.ogg** format and place the various types of notes supported by the game for each desired difficulty level.\
Upon completion, the software automatically generates a folder that you can place in the game directory to play with your own tracks.

![278325611-c34f5d47-8b68-4577-a477-68e653b9f423](https://github.com/glitchrstudio/tfeditor/assets/149059377/347e212a-8443-458f-bac4-1e1595b142e6)

## Getting Started

Download the latest TF Editor build on [releases page](https://github.com/glitchrstudio/tfeditor/releases) and unzip it anywhere you want. Launch **TF Editor.exe** and start creating.\
TF Editor is provided with a sample project, feel free to take a look on how an official song has been created.
> Please note that TF Editor can only run on Windows machines at the moment.

## Edit metadata

The first thing to do on creating a new track is to fill the song metadata.

![278328102-a7451a41-9bb4-4c15-9ccf-1b236c262289](https://github.com/glitchrstudio/tfeditor/assets/149059377/0f9617e2-a46b-43da-a58a-06ce4a2489a7)

| Metadata  | Description |
| ------------- | ------------- |
| Song name  | Track title that will be displayed on Track Select screen  |
| Artist name  | Artist who composed the backtrack  |
| Mapper name  | Mapper who designed the difficulty notes (optional)  |
| Version  | Version number for the track, you should increment it each time you change difficulty notes or medal scores |
| BPM  | Backtrack beats per minute, mandatory because it has impact on the notes grid generation |
| Time signature  | Amount of beats in one bar (optional)  |
| Song file  | Backtrack audio file used for playback (ogg or wav)  |

## Create a difficulty level

Taiko Frenzy offers 4 difficulties for a given track: Easy, Medium, Hard and Expert. A track is considered valid if it provides at least one difficulty level.

![278334015-7828659d-f1df-41b2-9866-15450cc398cd](https://github.com/glitchrstudio/tfeditor/assets/149059377/3c7b2ac1-2dbf-4bd8-af4d-c5f5976c2c26)

To create a new difficulty level, click the `+` button corresponding to the difficulty you want to create (Green = Easy, Blue = Medium, Orange = Hard, Red = Expert).

![278336734-8ec754a9-fccb-4dff-a151-4a67bcef9719](https://github.com/glitchrstudio/tfeditor/assets/149059377/091750c6-418a-47bb-a1ae-803a26ba639a)

Before you begin positioning notes on the grid for a particular difficulty level, it's essential to adjust the **Beat division** to your preferred value. This setting divides each beat into multiple sections on the grid and determines how the notes will snap into place when you put them.

> Please be aware that the editor does not permit freeform note placement; it always snaps to a beat division to ensure accurate rhythmic alignment.

## Position the notes on the grid

After choosing the desired difficulty level to work on, you can begin adding notes to the track.

![278340369-06b98f22-d552-431a-9c34-c6d6edcfcfa0](https://github.com/glitchrstudio/tfeditor/assets/149059377/4d475029-1840-4823-8813-f06ca52db9bb)

To create a new note, select the desired note type from the left toolbar (you can either click the button or use the corresponding keyboard key), and then position your cursor on the grid where you want to place the note. Next, `left-click` to add the note. If there's already an existing note at that position, the new note will replace it.

If you want the note to be accentuated (hit harder), you can hold the `Alt key` while left-clicking.
> Please note that this does not work on rumble notes.

![278344657-bb39cb9f-ac9a-4896-a758-f47771610f15](https://github.com/glitchrstudio/tfeditor/assets/149059377/faf0d28e-c1c1-4c6d-959f-1ac510b55c81)

To set the note length for rumble notes and determine when they end, you can adjust their settings. You can also position a note after the rumble to automatically limit the note length slider.

For deleting a note, simply `right-click` on it.

![278347135-d38dd8f1-d578-48b5-bcfa-ca00a763ce14](https://github.com/glitchrstudio/tfeditor/assets/149059377/566ca03e-0a32-445e-9add-855947c1d8e5)

If you wish to select multiple notes simultaneously, use the selection tool and click on the desired notes while holding the `Shift key`.

![278346425-866ffa5d-4051-4895-8f55-42d43ff0f970](https://github.com/glitchrstudio/tfeditor/assets/149059377/accb3e9d-8ad5-4e07-a31f-1ad2499a8266)

You can scroll through the backtrack using the `mouse wheel` or the playback slider at the bottom of the window. To change the zoom level for the editor grid, use your mouse wheel while holding the `Ctrl key`.

![278350124-709ed295-95f7-4598-b5c2-374499bdef27](https://github.com/glitchrstudio/tfeditor/assets/149059377/ba5b3bc5-f800-4517-825d-db71c2682045)

To create more refined variations across all difficulty levels, it can be beneficial to compare two difficulty levels. To do this, left-click on the difficulty level you want to edit and `right-click` on the difficulty level you want to compare it with.

## Design guidelines

With our experience on creating all the tracks for Taiko Frenzy, we think that these guidelines might come handy in your level design process:
- Avoid using too much rim notes in your level, especially in lower difficulty. As a rule of thumb, we found out that keeping a center/rim ratio around 70/30 can offer satisfying results.
- Avoid putting accented notes on rims
- Keep accents count on a reasonable level, you don't want the player to hit hard every note of your track, around 10% is fine
- Avoid chaining a center note and a rim note on the same side on high BPM tracks, it's better to alternate sides
- Avoid long rumble notes as it might be considered boring for the player

## Play your custom track

Once you've finished your modifications, don't forget to save your project (`Ctrl + S` or `File > Save`). You can now go to your project folder and check that the track is complete.

![278353238-c99bca80-b2df-4d8c-b728-3fd0e3eb17cb](https://github.com/glitchrstudio/tfeditor/assets/149059377/7406f586-d34a-4d33-a46e-4f9432f6033d)

A complete track consists of: 
- an **info.dat** file listing the metadata,
- one or more **difficulty map** files named *Difficulty*.dat,
- and a **wav or ogg file** corresponding to the backtrack.

If your folder is complete, you can now copy it to the game folder:
- **On Meta Quest**, connect your headset to your PC, enable USB transfer, and place your folder in `Android > data > com.GlitchrStudio.TaikoFrenzy > files > Tracks`
- **On Steam**, place your folder in `C:\Users\USERNAME\AppData\LocalLow\GlitchrStudio\Taiko Frenzy\Tracks` Replace *USERNAME* with your Windows username

If the **Tracks** folder doesn't exist, you'll need to create it.
