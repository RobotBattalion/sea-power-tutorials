# How to Create A Mission Briefing

## Assumptions
- Your mission is saved within a folder from the default location
    - Windows: `C:\Program Files (x86)\Steam\steamapps\common\Sea Power\Sea Power_Data\StreamingAssets\user\missions\user_missions\Mission Folder`
    - It is recommended to create a separate folder per mission

## First Steps

1. Open your mission in the mission editor
2. Select the Mission Briefing Tab
3. Select "Pick Assets Folder"
4. Navigate to `\user\missiomns\user_missions\Mission Folder`
5. Create a new folder here named `assets`
7. Select the new folder and click Open

## Add Briefing Text

1. Create a new file in a text editor, you will have to copy and paste this text as the mission editor is a simple text container
2. Draft your briefing. It is best to stick with simple paragraphs as the formatting is a limited xml format
3. Surround your briefing with the tags `<TextBlock></TextBlock>`
4. Add `<LineBreak/>` every 100 characters, as the lines will not wrap
5. Add `<LineBreak/>` at the end of every paragraph
6. Add an additional `<LineBreak/>` after every paragraph to space the paragraphs apart


### Example Briefing
```xml
<TextBlock>
Lorem ipsum odor amet, consectetuer adipiscing elit. Gravida egestas sed risus porta mus<LineBreak/>
 facilisi posuere torquent. Dolor ipsum pellentesque sagittis lorem parturient. Vehicula quam<LineBreak/>
 blandit in risus litora vel cursus dapibus ipsum. Efficitur tortor consequat quam ligula<LineBreak/>
 natoque montes vehicula consectetur urna. Urna quis nascetur commodo luctus iaculis quam.<LineBreak/>
 Felis hendrerit mauris aenean vulputate enim at, sociosqu hac. Libero faucibus sapien sed<LineBreak/>
 interdum purus class laoreet habitasse. Interdum dignissim fusce eget, ipsum ullamcorper<LineBreak/>
 massa ridiculus justo tristique. Tristique vehicula venenatis volutpat nisi amet.<LineBreak/>
<LineBreak/>
Orci nullam diam neque conubia turpis augue proin accumsan tristique. Pharetra sit ornare;<LineBreak/>
 habitasse consequat natoque eleifend viverra. Urna inceptos sed sollicitudin dui consequat<LineBreak/>
 facilisis est pharetra. Arcu magnis maecenas volutpat donec eleifend. Habitasse semper<LineBreak/>
 bibendum non, aliquam proin leo. Dui nibh magna nunc; rutrum laoreet rutrum cubilia. Penatibus<LineBreak/>
 sapien nibh habitant dis viverra feugiat curae. Dictumst velit vehicula mauris facilisis semper<LineBreak/>
 semper curabitur facilisis urna.<LineBreak/>
 </TextBlock>
```
7. Copy your briefing to the clipboard
8. Back in the Mission Editor > Mission Briefing window, select `Expert Mode`
9. select the empty pane and paste in your document
10. under `Left Pane` click on the `Update Left Pane` button, your text should show up on the preview

## Add Briefing Image
1. In your file browser, navigate to the `assets` folder you created during our first steps. Add your custom image to this folder.
> [!IMPORTANT]
> Images can only be of the following formats `png, jpg, & bmp`
2. In the Mission Editor > Mission Briefing window, under `Right Pane` select `Expert Mode`
> [!CAUTION]
> You may need to pick the assets folder again so the images will appear under the `Assets` section
3. In the `Right Pane` textarea enter `<Image Source="{Binding Assets[IMAGE_FILENAME]}" />` where the IMAGE_FILENAME=filename without extension (see example)
4. Click `Update Right Frame` and it should show up
5. Save your mission, the mission editor will save two xml files to the `assets` folder. The contents of this folder will be important later when you publish a mission.
## Example
```
<Image Source="{Binding Assets[1373px-Uss_iowa_bb-61_pr]}" /> 
```




