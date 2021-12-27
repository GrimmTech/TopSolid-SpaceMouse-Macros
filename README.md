# TopSolid-SpaceMouse-Macros
Macros for TopSolid linked to 3dconnexion Spacemouse

This Project was created to improve the 3dconnexion SpaceMouse while using TopSolid. It does so by linking custom TopSolid macros and Icons to the 3dconnexion GUI.

Instructions:

1. Backup your 3dConnexion TopSolid profile.
2. Backup your TopSolid Settings by navigating to Tools> Manage Settings>Export Application Settings.
3. Import Settings.TopSet by navigating to Tools> Manage Settings>Import Application Settings.
4. Close Topsolid
5. Navigate to C:\ProgramData\3Dconnexion\3DxWare\Cfg and place the Topsolid.xml and the images directory (with contents) there.
6. Start TopSolid
7. Within the 3dConnexion GUI map your TopSolid commands to which ever button you would like.



Creating your own custom Macros and Icons.

1. Within TopSolid Navigate to Tools>Customize and create a macro (shortcut). For example the Pocket command is mapped to Shift+Alt+Q.
2. Within the 3dconnexion GUI create the same macro.
3. Open the TopSolid.xml within AppData\Roaming\3Dconnexion\3DxWare\Cfg You will have some code that looks similar to the code below:

    <MacroEntry>
      <ID>Pocket</ID>
      <KeyStroke>
        <Modifiers>
          <Modifier>Alt</Modifier>
          <Modifier>Shift</Modifier>
        </Modifiers>
        <Key>14</Key>
      </KeyStroke>
    </MacroEntry>
   
Copy that code and place it under the other macro entries in the C:\ProgramData\3Dconnexion\3DxWare\Cfg TopSolid.xml

4. To link an icon with the above macro you will need to crop a 24x24 or 48x48 .png image of the command and place the image into the C:\ProgramData\3Dconnexion\3DxWare\Cfg\images\TopSolid folder.
Then you will need to modify the code below to link to your new image and macro. Do so by changing the ID, Name and image source.

    <ButtonAction Type="Macro" xsi:type="ButtonAction_Macro">
      <ID>Pocket</ID>
      <Name>Pocket</Name>
      <Image>
        <Source>[ts_images:PocketIcoTrsp.png]</Source>
      </Image>
    </ButtonAction>
   
 Place the modified code into the C:\ProgramData\3Dconnexion\3DxWare\Cfg TopSolid.xml under the ButtonAction section.
