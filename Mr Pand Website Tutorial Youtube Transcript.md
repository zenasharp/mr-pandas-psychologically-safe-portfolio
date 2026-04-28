![](https://www.youtube.com/watch?v=AD01pTr3gvw)

## Transcript

### Introduction & Showcase

**0:00** · Hello everyone. Welcome back to another video. So, this is still a work in progress. There's still a lot that I have to refactor and go back and refactor, but I just wanted to make a quick video on, you know, some of the more quote unquote advanced aspects of building something like this. So, it's a very simple scroll to navigate website with just minimal animations and so on so forth. I was planning to cover a lot more advanced things, but then I was like burning out and whatnot.

**0:26** · Yeah, the whole premise is just like how to make a looping thing like this and my updated methodology for creating custom camera path curves. I know there's like the.js which I don't think they've um released version 1.0 yet, but if you don't use the.js, this is like an alternative version and it's better than the one that I did in my Minecraft video. So, and then I also want to talk about my updated Blender workflow, which is like a huge portion of this video.

**0:55** · By the end, you'll be able to know how to create all the the simple stuff in between because we covered all the quote unquote more advanced things at the start. Then at the end, I just talk about some ideas that I quickly vibe coded in with AI and then also a little bit throughout the video like how you can use AI to help speed up your workflow and things like that. So, it's kind of step by step, but it's also more just like have your own project that you're working on that you want like a camera movement or something like that rather than use my assets and things like that.

**1:25** · Of course, you can always get all the assets usual for free on my GitHub. You can check the Blender file.

**1:32** · You can also check all the credits there as well. But yeah, just come over here.

**1:35** · There'll be a link for the Blender files. I haven't put it in at time of this recording, but it should be there later. But again, just follow with your own project rather than following what I'm doing and apply what you know for sure. But yeah. Okay. So, when it comes to prerequisite, it's pretty sparse.

### Prerequisites

**1:51** · It's a fairly simple website. I think just typical basics of React 3 fiber and 3GS basics of AI. And when I say AI, I don't mean like agents or whatever. Just like literally just asking an LM like what to do. Like you don't have to be like a prompt engineer or whatever they call it these days just as long as you have used an LM before. Basics of GAP would help a lot but if you were familiar with like this stuff then you should be able to pick it up.

**2:19** · Lennis is some other tech not required to know before but like again if you can understand GAB then you can probably understand Lennis when we use it. And per usual call out my mistakes if you see one. Again, when I make these videos, I'm also learning as I make them, and I continuously update as I learn new things cuz I'm still kind of new to it myself. Like, I just started YouTube as a hobby rather than like for anything other than holding myself accountable and like possibly helping a few people out there.

### (Optional) CALL OUT MY MISTAKES!

**2:49** · So, I don't know why I got an audience cuz some of my past code is terrible. But like yeah, just call out my mistakes if you see any. Like I'm I'm just like a regular dude with a YouTube channel. I'm not like a special coder. There's like a ton of other way better coders out there. By the way, if you're ever stuck or would like to chat with me, I'm on Discord like 247. So, you can just come over to over here and just join right there. Uh, but yeah, so thanks much for stopping by and let's get straight into the video.

### (Optional) COME JOIN US ON DISCORD!!!!!

### High-level overview of asset creation for more advanced people

**3:16** · So, this project is just like a better version of this project. Now, there's a few things in this project that I did not do in this project, but mostly this video is going to be better than this one. But I'm going to refer to this one a lot because I just want to talk about my design decisions here and the concept is basically the same. So let's get into the Blender portion.

**3:38** · So if I go into Blender and just click on any one of these, it's in a node group, but at the end of the day, it is just an transparent image mixed with another image here, which is a paper notebook image. So, if you already know how to draw stuff and export it as a transparent PNG or transparent image, by all means, go and ahead and do that. The next part is totally optional. There's a lot of alternatives to Critter if you don't want to use it, like Clip Studio Paint. Affinity is becoming really popular among designers and drawers.

### (Optional) Alternative drawing softwares

**4:10** · Procreate hugely popular. Adobe Photoshop still a standard. Critter, I really like Critter because it's like Blender. Like Blender to the 3D community is like Critter to the drawing community. So, I really like it, but it's totally up to you. And Critter is 100% free as well. Okay, so once you download Critter, if you open it, you can create a new image right over here.

### (Optional) Basic Krita Tutorial

**4:31** · Obviously, if you're a professional, you're probably going to have some preferences here, but if you're just starting out for the first time, just start with a regular, you know, cube.

**4:40** · So, 30,000 by 30,000. That might be overkill. That's a pretty large image, but honestly, it doesn't really matter.

**4:46** · Just focus on having fun. If you want to worry about these things, you can totally worry about them later. And I'm just going to create that canvas. So basic controls is just middle mouse button to pan around. Click down and pan around. And zoom in and out is like most other softwares, which is just your middle wheel zoom in and out. If you're using a trackpad, the equivalent to whatever the middle mouse button operations are, are probably going to be working as well. There's a lot of amazing more detailed critter tutorials on there online for beginners. I'm just showing you the absolute basics that you need to know. Okay.

**5:16** · So, by default, you have a lot of tools here. I'm just going to be focusing on the brush and fill tools, which you've probably seen before in many, many other softwares. Critter has them as well. Over here is your layer system. So, you can think of these like sheets of paper. You draw on every single sheet of paper. So, if I want to create a panda real quick, let me just change the color over here to black. On the brush tool over here, you can see there's some size changes over here.

**5:44** · There's hot keys for that and it doesn't really matter. Anyway, I can just start drawing. Left click and drag and just draw, you know, my panda over here.

**5:53** · Super cool. And if I want to erase, I can change it to an eraser over here just by clicking on that. And now you can see I can erase just a little bit over there. And just over here.

**6:05** · And then I can use the fill tool by hitting F or coming here and clicking on that. And then I can just change it to wherever I want. So maybe I'll change it to white over here and just fill it. Now we can't see it because the background itself is white. So we can just hide it.

**6:20** · And now we can see what is going to be transparent and what is not. And then the ears can be black. So I'm just going to fill that in with black. Switch back to my brush tool. And then continue drawing the face there. And there we have our panda. And that's going to be right there just like so. So I'm going to hit F and just fill like so. And the really cool thing is that everything can be an eraser. So if I come to the bucket tool again or the fill tool, hit eraser and click on this, it's going to make that entire thing transparent. I'm going to hit Ctrl +-Z to undo that.

**6:51** · And then yeah, just use B a lot. And make sure you're not on eraser cuz sometimes you might accidentally erase stuff. Of course, there's a lot of other tools, a lot of things to prevent you from drawing outside and things like that, but I'm not going to be covering that in this video. So I'll just come over here and rename our layer. So you can imagine when you're making a moving device, if you want to target it, put it on a new layer, you can right click over here and duplicate that layer or use the hotkey control J. Or you can also come down here and just create a PL paint layer.

**7:25** · There's other kinds of layers here for more advanced stuff. But by default, it'll just add a paint layer, which is mainly what we're going to be using. So let's call this bike. I can hide the panda over here, and I'll call this bike body, actually. So, I'm just going to draw a bike real quick. I'm going to use black. Use whatever color you want to use. And this will be our bike. I'm going to create another one. I'll call it bike front wheel.

**7:52** · And here, I'm just going to draw over here. And because it's on a separate layer, you can see that it's not going to affect the ones below. So, I can toggle that on and off. I can also adjust opacity here if I want to see the things that I'm drawing a little bit easier. And sometimes you might be active on one that's hidden and you only see the bike body and you're trying to draw and you won't see an issue. It's because you have to keep that highlighted if you want to draw on that one. Cool. And now I'm just going to right click over here. Well, actually, let's use a hockey this time. Ctrl J.

**8:26** · Copy of front bike wheel. I'm going to actually use the transform tool here.

**8:31** · And I'm just going to move that over there. And I'll call this bike back wheel. Like so. Cool. So now we have Panda. And I think Panda needs a body real quick. So I'm just going to hit B and just draw him a body real quick. And make sure to fill in the gaps so Critter can autodetect it. If you don't, it'll it will not fill appropriately. Of course, there's other ways to handle that, but since we're just starting out, just make sure to fill that out there.

**9:00** · And I'm just going to fill that in with white. You can hold control to quickly eyropper tool and select a color. I'm just going to click that just like black. And I'm just going to fill that out like so. So now we have a bike like so. And a panda. And now we can just get ready for export. So let's come over here to tools scripts export layers. And we don't see anything because I did not save the file. So let's actually control S. And let's just name it tutorial pana and save it.

### (Optional) Exporting Image Assets from Krita

**9:27** · And now we can come over here to tools, scripts, export layers, and we can select the document that we currently have open. If you have more than one document open or project file, you see multiple. I'm just going to select the one that we just saved. And you can select your output directory wherever you want. And now you have an option here either to export as a standardized size that you choose. By default, it's going to be the size that you set. We set it to 30,000 by 3000. Or you can adjust the export size to the layer content itself.

**9:57** · So let's say if I made the panda like this big, it's only going to export like I don't know like 400x 400 pixel panda. Whereas now if I keep it at 33,000, it's going to export this entire thing and this entire huge area is going to be transparent. So when you're making different outfits for the panda, let's say I come over here, let me just do that real quick. I'll call this samurai. pund raw panda. Let me just hide these other ones. Uh website moved it. Doesn't really matter.

**10:28** · You can move your layers if you want to click and drag on them, but it's not a big deal for most things uh that we're doing anyway. And I'm just going to let's see, hit B real quick and give him an epic super super epic sword over here. And I'm not even thinking about it. I'm just going to fill it with some colors. And oh, here we can actually go here, hit the eraser tool. Uh, well, actually, this would be easier just to brush over it instead of erasing. Cool. So, now we have a samurai. Whoops.

**10:58** · I'm holding shift and middle mouse button to rotate it. Uh, so yeah, basically we have panda, original panda, and samurai panda. Now, anyway, when you're making like different stuff where everything else stays the same, that's kind of when you want to use the entire canvas cuz it's just easier to work that way when you're doing it in Blender. So, let me just Ctrl + C to copy this. Let's create a new file just for organization. I'm just going to create it. I'm just going to save this one. I'm actually going to whatever. Name it whatever you want. And I'm just going to Ctrl +V to paste it over here.

**11:30** · I'm just going to delete this one real quick. Now, let's do tools.

**11:34** · Same thing. Export layers over here. And this time, I'm going to select actual Panda. And here, we want to use PNG because it supports transparency.

**11:43** · There's other ways to export in Critter.

**11:44** · I'm just doing it this way because it's the fastest. And I'm just going to hit okay. And since we're here, let's just export the other one as well. And this time we're going to adjust export size to layer content just to see the difference.

**11:56** · Here for this one, if I right click over here and take a look at properties.

**11:59** · Let's go to details. You can see is 446x 502 pixels. And this one is probably something different because I drew it differently. So if we also check over here, you can see 1477 by 93 or whatever that was. And of course, when I do these pandas now, they're going to be 3000 by 3000, both of them. Okay, let's create a new Blender file. I'll try and say everything that I'm doing out loud. And if you are ever confused, just drop a comment down below and I'll get back to you as soon as possible. Okay, anyway, first thing we're going to do is shift A and search.

### (Optional) Basic Blender scene modeling with textures

**12:30** · Just start typing and search for a mesh plane and then just navigate to wherever you saved your stuff and then just open it like so. And if I go into rendered view here, you can see that it's already going to map that up for us. Let's just create a new food port over here. Shader editor here. You can see it's just an image and it hooks up the alpha channel to the principled BSDF. So it cuts it out just like so.

**12:53** · Super cool. Let's go and add some world lighting right now. Let's grab it that sky texture as usual. That's the one that I used. It's way too bright. So we can turn it down to like 0.4 and 0.5 or whatever aesthetic that you want to make it. RX90. Let's just scroll that up. And now the light source is over there. You can just rotate it. Let's say 180 degrees. So now it's coming from this side over here. And we used black, but it looks gray because the lighting is still really, really bright. But up to you how you want to do the lighting.

**13:22** · So now we can just go into orthographic view. And the really nice thing is that mesh plane will also name it as your material for you as your image. You can always just shifty duplicate duplicate this. Let's go back to object and replace it this way. if you want to. You might have to make some adjustments and it doesn't really matter. Just make sure you don't stretch it too much on the UV, otherwise it might cause some issues when baking. But for the most part, that never happened for me.

**13:50** · So, if it starts like this and you just want to scale it instead of adjusting the UV, like of course the alternative is you adjust the UV instead. So, we hit A and adjust like so. That's another way to do it instead of the plane itself. You can totally do that. I never had an issue as long as it was in there. I didn't have an issue just scaling the mesh itself. And we actually technically don't need the back wheel because it's the same as the front wheel. If you had a different one, of course, you would duplicate again. And bike wheel. Uh, sorry, this one is front.

**14:20** · And then you just navigate to your front wheel. And then this one can be back wheel. And then we can bike back wheel. Not that those are different, but whatever. If you I had different wheels, so I had them as separate images, but anyway. Yeah. So now we have now we pretty much have our bike. Make sure to give it a little offset so they're not Z fighting and overlapping each other. As you can see that they were flickering earlier. Yeah, if you ever want to scale them, they're not working properly.

**14:47** · That's totally fine because you can just hit period and change to individual origins. And now you can see it's going to scale along the individual origins.

**14:54** · You can also come over here and change that over there as well. Bounding box is what you're typically going to use, but individual origins is also pretty popular as well. So, that's a good origin point for the wheels. Cool. And now I'm just going to add another mash plane over here. I'm going to add my panda over there. RX90. Just like so.

**15:13** · There's Panda. And now you can see that I only have to do one mapping for Panda over here. And when I switch, I can just switch to Samurai Panda. And you can see it's just going to replace there. And that's the benefit here of using a fixed canvas size. You don't have to make any adjustments. It's just going to flip right over there. If for some reason you're ever finding yourself doing this manually and as you adjust the UV map uh sorry the UV editing and it starts repeating like let me come over here. By default it'll be on repeat I think.

**15:42** · So it'll it'll just keep repeating the texture instead. By default mesh plane will leave it as clipped. So if you're doing it manually just make sure to leave it as clipped. All right. I'm just going to do this in control spacebar.

**15:57** · Let's now add a circle for our track that we're following. I will cover the infinite looping method that I did for the other website. Later in this video, for now, we're just going to keep it simple and just do a round circle. 128 is fine. Uh, you know, that's kind of up to you and how you want to work. I think 128 is fine. I'm going to go into edit mode. I'm going to hit E. And I'm just going to hit S. I used to rightclick cancel. I think that was an old Blender thing, but now I just hit S. You don't have to rightclick cancel the E operation before hitting S. I'm just going to scale it.

**16:27** · If you ever want to adjust it, just hit S again and then shift C just to make sure it's not doing it on the Z-axis. Cool. And that's kind of like our track. Then we can add like two loop cuts just to cut out the center. And select one with Alt GG. Just slide it in. Hold alt GG. Slide this one in. I don't know if you want to uh let's see, E extruded downwards or not. That's totally up to you as well. I'm going to select this with alt and just hit E and extrude that downwards as well. Cool.

**16:56** · And now we are pretty much set down. And I'm going to right click shade auto smooth. And now we can also just hit uh hold alt and select the outer loop and hit E and extrude upwards. And now we kind of have like our full rotating world that we're going to be working with. Super cool. Now we do want it illuminated. If you want to use an area light and just place it on top, that's fine as well. We can also just play around with the sun maybe a little bit more and play around with the elevation.

**17:24** · I think uh we can just put it directly on the top right. So that would be 90 degrees and um yeah that's always of course up to you and how you want to do things. Now you will notice these seem to have some opacity itself and that's because in Critter I left the opacity on here. So let's just make sure that all these opacities are turned up. This one was 97. So yeah, just make sure that the opacity is all. And the great news is you can just export to the same exact place. Just export layers. Same thing.

**17:57** · Navigate to the same folder. So make sure when you're navigating to reexport, you don't actually select the folder that you're exporting to. You select the parent folder, which is Panda first for me. And it'll generate you a folder based on your file name. So I'm not going to actually double click into this one. I'm just going to select the parent one, which is what I'm in currently. So same thing. Let's change this to PNG.

**18:19** · And like so, just hit okay. And now I just go back into solid view. Hit alt R to refresh the images. Let's go back into render view. And now you can see that we've got our updated super cool stuff. Just like cool. Now I don't like moving all of these at every single time. It's a little bit annoying. You can move it into a new collection too, but we might as well just start with some parenting right now. So I'm going to shift right click. I'm going to add a cylinder. Now we're going to be really far from it. So I think 14 is more than enough. You could probably even go lower. and no one could honestly tell.

**18:50** · Um, but I do 14 that way this shade auto smooth doesn't have like a harsh line on it. Honestly, again though, no one's probably going to look, especially when it's this small and this thin. You could probably get around get uh off with eight. Yeah, honestly, I would use eight. I don't know why use 14, but yeah. Um, yeah. Anyway, just select these. Select this one with shift. Make sure it's active. Control P. set object to parent.

**19:18** · And now we can just uh adjust the stick and adjust everything else while these remain its own rotation. And we can rename it bike stick. If you want, you can open this up. And of course, we also want to rename these cuz we want to target it later. It'll just be easier just to uh bike back. It'll just be easier to see that in code. Just going to copy and paste that. And I'm just going to Well, super cool. And I'm just going to position panda accordingly.

**19:47** · just like so. And of course, since we're on the stick, we might as well adjust its origin point. We are pretending that we're holding it from the bottom. So, let's go into local view real quick.

**19:57** · Let's go to an orthographic. Hit control period GZ. And this time, I want to turn on snapping here. So, let's turn on snapping, but let's do edge. Hold shift face and uh vertex.

**20:10** · And then GZ, and then just hit control.

**20:13** · And then, actually, we don't want to manually do it. We'll just uh use the hotkey of controll G. Hit controll snap the origin point to the bottom. Just like so. And controll period to confirm that. And now there we have our stick over there. Now it is adjusting the position of this. But that's totally fine because we can just select them and just G Z and move them up. And we can still adjust the stick accord. Okay.

**20:37** · Since we're on the stick using our Blender Kit add-on over here, let's just click on our stick. Give it a new material. You don't have to rename it cuz Blender kit material. Rename it.

**20:49** · Let's open up here. Let's just search for something like wood. I don't know, honestly. Just use whatever you want to use. And I'm just going to click and drag that right on there. Honestly, it's so far away. No one's going to be able to tell how good it looks. But if you want to just apply scale and just give it a quick U smart UV reject unwrap um you know and then we can just create a UV editor here and just hit A and maybe scale it up. Let's see. Scale it up. I don't know. Yeah, no one's going to tell cuz it's so far as long as there's something on there.

**21:20** · Now for the paper I used it is belongs to another YouTuber. He's super popular. Definitely subscribe is a crafty asset pack. That's where I use my notebook. But you don't have to use that. You can just go on to Google and like look up notebook paper texture and you can see one right over here on Freepick. Just make sure to create accordingly. You can also create your own notebook texture if you want to, but it's up to you. And now all we have to do is just mix it in with our image texture. So here, uh, I'll just call this notebook for this one.

**21:50** · And I'm just going to shift A and add an image texture over here. Navigate over here and hook up in there. So now we should see our thing, but we don't. And it's probably because we need to unwrap it.

**22:06** · So let's control a apply scale. U reject. And yeah. Okay, now we see it.

**22:11** · And we can just scale it up like so. And if you want your paper to look bad that you can totally do that or you can go into edit mode, R 90. And now we just now it's just we can just scale it however we kind of want it. So that's up to you how you want to UV unwrap it. I'm going to turn off overlays here cuz it's a little bit distracting. You can also do that with altshift Z and I'll turn that all off as well. Or you can just come over here and toggle the ones you don't want to see like the axes and the floor. I don't want to see those.

**22:44** · There's also probably some other cool paper ones that you can find over here uh if you want. Oh, that's pretty cool.

**22:49** · You could do like a grid paper sort of style which would be honestly pretty cool as well. I think I have to redo the unwrap which is why it doesn't see there or it's like a let me see. Yeah, I just have to re redo the unwrap there. And now we have like grid paper. That would be a pretty cool portfolio as well. A full cardboard world would be pretty cool as well. Anyway, yeah, it's totally up to you. So, whatever whatever floats your boat. I'm just going to go back for this free pick one. Now, for these other ones, we just mix the image color data with it, right?

**23:20** · Like we did in previous videos. So, I'm just going to Ctrl + C and then switch to Panda. Ctrl +V over here. Go over here. Search for a mix color node. Color one over here. Color two over here. Slap that in right there.

**23:35** · Change this to multiply. And now you can see we have the grid lines over there.

**23:40** · And then we can just crank up the factory slider. Or alternatively, you can use the alpha channel to drive the factor slider. Same exact effect here as well. Again, we covered the math behind this in my room video. If you want to take a look at that, you can totally take a look at that and how that works there. Now, the one in the crafty asset pack had a roughness map associated with it. You can create your own or create a custom roughness, whatever. Or or you can just crank it up to one or wherever.

**24:04** · Paper's pretty rough, so you can just crank up the whole thing to to uniform roughness. Honestly, no one's really going to be able to tell. All right. And if you want to adjust this paper texture, you can just do CtrlT with the node wrangler add-on, right? And you can adjust the scale here. So maybe I want a little bit bigger. I'm just going to hold left click, drag down, and change this to 0.5. If you don't want to click, drag down every single time. You can just search for a value node over here.

**24:30** · You'll just input a uniform value across everything. So 0.5 or something like that. And now it's a little bit bigger and we get that red line, whatever you want. Now, one downside of this approach is you can't independently adjust the UV map, otherwise you're going to mess up the panda UV map. So, if I come over here real quick and let's just go to Panda Samurai Samurai Panda and take a look at the UV. It's right. It's mapped to the 3000 by 3000. And as I adjusted, that paper is also adjusting there. Of course, I can translate it here as well if I wanted to do that.

**25:03** · But if you wanted your own UV map, you can just come over here and call this paper UV map, right? Just like so. search over here and add a UV map right over here.

**25:16** · And we can plug this into the vector over here. And then here we can say select paper UV map. And then paper UV map by default is using UV map cuz we based it off of that one. But now we can adjust the this one with highlighted. We can do smart unwrap. And here you can see that it's going to be based off of this UV map now of course. And then you also have, you know, all your other stuff. You can also just directly put it in there if you want to, but uh yeah, whatever you want, whatever floats your boat. Cool.

**25:44** · So now, anytime you ever want to use this material, I guess we should have done this first before I added these. All you have to do now is just shifty duplicate this and duplicate over here and call this like dragon bazooka or something like that. Whatever whatever asset you exported. And then now you just navigate to your next thing and it's going to use all the same defaults that you have in there as well.

**26:07** · If you want, you can put all of this into a node group so it's easier. Just do Ctrl + G and hit tab to go back out.

**26:15** · And then you can just call this paper combined, whatever, whatever you want.

**26:20** · And uh now you just have like a general thing. Hit tab to enter and tab to go back out. And if you want to add some controls, just go into tab over here, group, maybe we can select scale. We can get rid of this. If you want location, too, we can also do location. Let's hit tab to go back out. Let's add the value over here. Let's just copy and paste 0.5 over here. Whoops, I copy and pasted the wrong thing. That's fine. We can just delete that and over there. And now we have the full controls over here as well. So yeah, it's just plugging in into this over here and so on so forth.

**26:51** · So we actually don't need this anymore.

**26:52** · Okay, now it's in a no group. Be careful when you duplicate it and switch. Let's say you duplicate it and you go over here and then you switch this to something else. It's going to affect the first one. So, make sure to come over here and click this. So, it makes it a separate one itself. And now you can go over here and change it to the panda one. Okay. So, let's just do a quick test export. I'm going to hit A to select everything. File, export, glTF.

**27:20** · It's fine if you select your camera.

**27:21** · We're that's just a test. Only selected objects. Remember, export settings.

**27:25** · Cool. Uncheck animation. Nothing there.

**27:27** · And material. We're going to be exporting the image materials this time.

**27:30** · So use any gltf viewer online if you want to or the 3GS editor online itself and just upload your stuff. Now the whole reason I'm doing this test export is just to show you what it would look like if you did not bake it. For the people out there that don't want to bake but want to do still a handdrawn or illustrative sort of portfolio. For example, something like this except in 3D rather than 2D, you can totally go for that. And that's all just to show you here. like what you draw on Critter is going to look fantastic in in here as well. Of course, the lighting is a little bit off.

**28:00** · You can adjust that as well if you're using real-time lighting or whatever. For the people that do want to bake, you can see that the lines on the panda or the notebook paper isn't showing up. And that's because this multiply node does not export properly in the GB file. But since we're baking, it's going to be part of the image texture that we bake, too. So, it's not going to be an issue for us. But I just wanted to point that out, right? Of course, for the people that still want to go illustrative, but still want the notebook, you can only just bake the diffuse and the color rather than the lighting as well. I'm going to be baking the lighting and the diffuse.

**28:29** · Okay, so I just spent some time drawing a bunch of random stuff. Now, if you want to select it, make sure to hit F2 and rename it.

**28:38** · If you don't want to select it, you can join it with other static objects like this tree over here. You can probably just Ctrl J and join that together. So, it's a single object just to for optimization purposes. And sorry, when I mean select, I mean in code. Like if you're not animating it or want to target it later, then just join it into a static object. Of course, it depends on how you want to split up your baking.

**28:59** · I have so few here. It probably doesn't really matter which ones I join together. I probably can figure something out regardless. All right. So now, if you want to just change the color of like the notebook, like let's say you want this over here to be like a different color. So I'm going to hit shift alt just to select over those. If you want this to be a different color, you can add to the material. Create a new one. Let's just select notebook over here. Duplicate it. And lots of ways.

**29:24** · There's the hue saturation node. You could do a color ramp. You could do a color ramp. You could do a hue saturation. You could do a curves adjustment layer. You know, whatever you want to go for that way as well. But I'm going to be texture painting because I want to add a little bit of detail there. So, since we're on this topic, we might as well go into local view with slash. And we might as well get rid of these things that we'll never see. Of course, that depends on your portfolio, but I'm just going to delete those because we don't need them. Same thing on this side as well. I'm going to delete those faces cuz we'll never be seeing them. Cool.

**29:55** · So, let's create a new image here for our texture painting.

### (Optional) Basic texture painting setup

**29:59** · And I'm just going to search for an image. Shift A. And let's create a new one. I'm going to make this 4D96x 4096. 32-bit float just for some better color. Alpha is fine. I don't think we'll be using that, but I'll just leave on the transparency. I'm going to start it from a white. And I'm just going to call this terrain, but you know, name it whatever you want. And I'm just going to create that new image right there. I'm going to come over here. Shift A. And you already know what we're going to do.

**30:27** · We're going to search for a mix color node. We're going to put the color over here and the base color over here. And just mix it just like so. And here we're going to choose a multiply again. Now, the UV mapping for this texture over here, as you can see, is very not that good. And we don't want to texture paint like this. So, you already know what we're going to do. We're going to come over here, and we're just going to come over here. There's an auto map here.

**30:54** · That's so weird. Is that is that from myself? Or that might have been from the texture itself that I was using when I was switching between stuff. So, generate auto map. Some of the Blender kit ones have an auto UV map. So overwriting that when I was unwrapping manually, but doesn't really matter.

**31:09** · Let's add that second UV map. And let's call this for terrain UV or whatever you want to call it. You know, up to you, up to you, up to you. Cool. And let's just go back and use that. So let's come over here. And this one, let's search for a UV map. And this time we're going to choose the terrain one. And then shift duplicate this one. And this one's going to use whatever you called it. Mine is auto map, so I'm just going to put it auto map. So now we can come over up here to texture paint and we can change to terrain. Cool.

**31:39** · And let's just make sure we have that highlighted in UV map terrain. Cool. Let's just U smart UV project unwrap. Now the unwrap isn't ideal. So I think we can just temporarily just adjust the UV. Uh let's go to the UV editor. And I think I'm just going to honestly just select everything as much as possible and um just add a bunch of edges because we don't really care about the unwrap uh whatever whatever. So that we don't really care about it whatsoever.

**32:10** · I just want to get um you know flat flat stuff.

**32:16** · So I'm just arbitrarily adding like lines to tell it where to slice for no particular reason for no particular any reason at all. Um, you know, it's it's uh just overkill at this point. But anyway, now control E mark seam. All right. So now we got a bunch of seams in place. Let's just U. And I think minimum stretch will be fine here. Cool. In previous videos, I covered how to uh fix the fix those alignments.

**32:42** · I'm just going to hit S to scale it down a little bit to like fix it so it's like in a straight line, but whatever. It's fine for us. And now we should just be able to texture paint. So, I'm just going to close that UV editor. Let's call let's just make sure our face orientation is correct as well. So, yeah, we're going to need to fix that. Let's do alt and flip. Okay, we don't actually need this first notebook anymore. So, we can get rid of that. We just need the one with the combination over here. I think in older versions of Blender, you have to keep this active in texture paint mode in order for it to know.

**33:13** · So, just do that as well. Let's go into texture paint. Now, with the brush tool over here, we should just be able to paint.

**33:21** · And exactly, we do. So that's all I'm doing there. Again, shift F to change the intensity if you want it to be 100%.

**33:27** · So I'm actually just going to fill everything a base color first. That'll override all my changes, which is fine.

**33:33** · I'm going to hit Alt S just to continuously save it. And I'm going to go back to my brush tool here. And I'm just going to continue drawing again.

**33:43** · F to increase the size. You know, however you want to stylize your scene.

**33:48** · Now, sorry, I accidentally got rid of the other notebook. Sorry. Let me add that back real quick because I don't want the side to be affected. So, I'm just going to select the entire ring over here and just assign that to the white color. If you want to paint the sides, you know, totally go for it as well. I might change my mind a little bit later. All right, let's go back to texture paint and just keep on painting however you want. If you want to go into top view, go for it. All right, just make sure to hit alt s and sweet. It looks pretty good.

**34:16** · And make sure since we're on face orientation, we might as well just correct the ones that are flipped. So, I'm just going to select these, go into edit mode, alt, flip, just like so. Cool. And now everything is facing the right location. Now, if you accidentally used a color that is uh, you know, a little too green. And now everything looks a little bit green, of course, you can just make it less intense and repaint. Or what you can do is just come back to the material itself.

**34:45** · And I think what we can do is probably just go for a hue saturation value over here and probably just turn down the saturation. Turn down switch the hue to something a little bit less and then even the value here which is like the brightness sort of thing. Uh so I updated my lighting by getting rid of the sunlight and just adding an area light on top here and giving a little bit of red to counteract the green tint.

### (Optonal) More texturing/design talking

**35:10** · Of course, it's really up to you. I don't know why I'm spending so much time on this project since I'm not going to be using it. Yeah, really up to you there. I just did that. Now, what we want to do is also set up our camera.

**35:22** · So, I'm just going to shift S cursor to world origin to make sure it's an origin. Everything else we kept and spawned in the origin. So, we can just do the same thing here. And we'll just add our camera. Now, if for some reason you're not at the world origin, that's totally fine. You can just select this object over here. Q said origin origin to geometry and then shift S cursor to selected. Sorry, with this selected cursor to selected and then spawn your camera in the center that way. But I'm at the world origin. So I can just do it and it lines up with the center here as well. Yeah, let me see. Yeah, it's at the center here.

**35:54** · So that's all great there. Let's go into zero just to go in numpad zero into enter into our camera view. Now it's at 50 by default. I think I'm going to go for a 35 sort of look over here. RXX. Just rotated RXX. RZ and just frame that in there. I'm going to do controlB for the render region just to make sure I know what I'm looking at.

**36:19** · That looks pretty good. Adjust your camera however you want to adjust your camera. All right, let's make sure our camera selected. RZ and just rotate around. Well, actually, I'm going the wrong way. Sorry. I'm just going to rotate counterclockwise just like so. Super super cool. And honestly, now that I look about it, it really does not look like paper at all.

**36:41** · So, you probably should use a PBR with like roughness and normal or you can just create it yourself real quick. So, I think the easiest way is just use the noise texture into the normal. And we'll just plug that in over here. Over here, don't see much. Let's preview that because it's really large. So, we can just increase the scale quite a bit. And now we go back and we still don't see anything. Maybe it's uh I think it's over here. We can increase that a little bit. Whoa, that's a little bit too much.

**37:10** · Let's just turn down the strength. Well, that doesn't really look Yeah, a lot more subtle there. And then maybe turn down the strength a little bit. That way, it just gives it a little more texture and kind of looks like paper. Or again, just use an actual paper PBR material instead of just using a image of a notebook paper on. Okay, so now I just want to talk about masks. This is a very very simple way just to quickly create textures. Like let's say you want to create leaves or like um you know some sort of like polka dot pattern or whatever some sort of repeatable pattern sort of thing.

**37:41** · You can just use it as a mask rather than different sort of colors. So here I'm just using black and it's on a transparent background. Just exported it as normally and I just duplicated the panda one. But instead of mixing the color, you can actually just use it as the alpha result itself. So let me just plug this in over here and uh unplug the alpha there. So this is by the default without mixing anything, right? It's just that paper texture that we used. And now all we can do uh we don't actually have to use this.

**38:12** · We can just use the alpha channel directly and mask it out like so. And oh, sorry, I'm still using the panda. So, let's navigate to our leaves PNG mask thing that we did. And now you can see that that's pretty much it. All the areas that were black are showing that original paper texture color there. And now, if you're like making a tree or something, you know, you could just like duplicate and rotate these around. If you want, you know, give it some subdivisions. Uh, sorry, I should probably just right click and subdivide it a few times. You know, turn on that proportional editing.

**38:42** · There you got some le textures or whatever you want to call those. Now, if you don't like it where you have to like go to your drawing software, export it, and then, you know, hit alt R on your Blender to reimport it, you can actually link your Blender editing the image into an external software like this over here. So, all you have to do in that case is just save it in your 3D software and hit Alt R in Blender to refresh the image and it should be fine.

**39:08** · Some softwares might have a little bit more steps to sync them up, but that is also an option if you want to do that. So, another tip I'll give is if you want to make things, you know, like curve to the surface, a really simple and easy way to do that is with shrink wrap modifier. And since we're working with simple geometries, it should work pretty well. So, if I just use it, you can see that it's just going to snap. And there. Now, you can see that, you know, it's kind of like wrapped to my surface over there.

**39:36** · If you ever want to add imperfections, you know, don't be afraid just to use the knife tool and cut it out. Like if you just want to save some space, you can also just cut out all the empty areas as well, like something like this and and just delete that if you want to. You don't have to, but if you want to, you can totally do that as well. Or if you want to make like scissors cuts, you know, just feel free to do that. No one cares about topology here. And then you can just delete those faces. Now, if you do adjust it, it might cause some stretching, so just be aware of that.

**40:06** · you might have to unwrap again. But yeah, so you don't have to rely completely on just drawing. All right, so I made a few updates to my scene over here. And now I just want to talk about, you know, the things I look for during baking. I do expect you to know what baking is, but I also just talk about, you know, how I would approach baking a scene like this. So just a quick refresher, baking is the idea that we're saving some amount of information so we don't have to do like all those mathematical calculations. You can see on this website over here, they baked the shadows in. That's why his hand is moving, but the shadow isn't over here.

### (Optional) Things I look for during baking large scenes

**40:38** · Same thing here. Her hair is her hair shadow was baked on here. And now it kind of looks a little bit off cuz it's like moving and the shadow's not updating or anything like that. But again, when the scene is so welldesigned or there's a lot going on, very few people are going to be paying attention to these details. And sometimes just having it feels better than without having it, even if it's static. So this is kind of the concept that I want to address.

**41:02** · It's like how do I intuitively know what should leave in a static shadow even if it's moving or what should I just remove the shadow otherwise it'll look a little bit awkward. Okay, so the first tip I'll probably give when it comes to baking scenes in in this sort of aesthetic where it's more like playful and like safer feeling or like calming feeling is to go for very diffused or the lack of hard shadows lighting sort of thing. You can see that there's no hard shadows in anywhere in the scene. It's very very diffused.

**41:31** · While that provides a sense of softness, what it also does is it makes it very very easy to quote unquote hide lack of realism stuff and still you know feel natural. So here you can see that given the lighting over here there is some shadow being reflected by the character over here but this character will be moving so it won't always be there and of course the shadow is going to travel with the character. However, we are going to be baking our scene and we're going to try and avoid real-time light.

**42:00** · So because we have this really soft looking shadow, if I completely remove this character, you can see we lose that shadow. But it doesn't really affect the overall noticeable of realism. Only someone that is very familiar with artistry would notice whether that deserves a shadow or not.

**42:18** · Because if I just move this character over here, you can see the shadow is also disappeared. So by using this diffused lighting, you can play with the benefit of doubt a lot easier on the human eye and human brain because if you used a very very hard shadow, a very hard lighting would expect to see some sort of shadow here. And if there's no shadow, then it would just be really weird. It's also easier to fake that shadow if you ever wanted to fake that shadow later because it's it's very diffused. You barely see a shape. So you could like fake it with like a sphere texture opacity or whatever and it would pass as a shadow.

**42:49** · Whereas if you have a hard shadow, it's a lot more hard more difficult to fake that sort of shadow rather than a diffused shadow. So just more intuition when things are moving, definitely give it, you know, completely flat lighting. For example, this bike over here, if you bake this bike when the paper is over the other one, you're going to have like a black line there, and every time you rotate it, that black line's going to follow, and it'll just look really off and odd.

**43:15** · So here you can see that everything that I have moving in the Panda website, I just separated it out. So the bike wheel is over here, over here, the bike body is over here, and then later once you're done, you can piece them back together after you're done baking. That way you never have like overlapping baked shadows. Now, the really nice benefit of using diffused lighting is I can just place these anywhere in my scene, and the lighting is going to stay very consistent to what it would look like if it was actually in the scene itself.

**43:45** · So, you can find these source files in the description below, so you can check that out. And then things that you have multiple of, you don't have to bake more than one. So, I had three of these in the experience, but I only had to bake one and then I just duplicated it. I didn't use instancing because it was just two more, but you could totally use instancing as well if you want more. So, also keep that in mind if you have repetitive things, you only need to bake one of them. You don't have to bake all of them. Of course, you don't have to, you know, stick with that. It's only if you want to like save texture space and save on loading time and things like that.

**44:16** · Like here for these grass objects here in these flowers, I could have just baked a single one and then for these other ones, I could instance them. I did not do that. I just baked all of them onto a single texture because I knew the loading size wasn't going to be that big and I just wanted to save time and move on to the next project. So, it'll just come over time. you kind of like get a feeling of when you can cut corners and it'll still be fine versus when you probably shouldn't cut corners. They'll just come naturally over time. Okay.

### (Optional) What should I bake together? Intuition Development and Developer Experience.

**44:43** · Now, I want to talk about like how do you determine which things you should bake together intuitively. Now, again, this is something that you get over time in intuitively, but I kind of want to stir this conversation away from optimization for a little bit and just like focus on developer experience and like your own mental effort and cognitive load.

**45:00** · So, we do know that if you select the right objects that pack together really well, that means you'll have the most optimal amount of texture space used on that specific image, which is great because that means you might be able to reduce the amount of pixels or amount of textures that you need later on. So, for example, let's say this tree over here and maybe this over here and this over here.

**45:26** · For best case optimization purposes, these are the ones that pack really, really well to each other on a texture. Am I going to bake them together even though it's the most optimal way to do it in terms of performance? And the answer is no, just because the coding experience for that would be a nightmare. Maybe that's an overexaggeration, but the way I like to put it is like you kind of think of it like a grocery basket in a sense. So, let's imagine you're shopping for oranges, green apples, and plums, and you're given three baskets.

**45:56** · You could theoretically add a lot more by mixing the plums and oranges to pack a lot better. And if you do it so well, you might not even need this third one eventually. So, you could just like pack everything in two over here. So, you can imagine one of these is like animations, like animation logic. The other one is just like loading texture logic and so on so forth. And while this would be best for performance, you know, maintenance, if you ever make a mistake, if you ever want to go back to it, it's just a much of a headache.

**46:24** · What I like to do is like, okay, maybe I just group things together. So all the animations for the third scene is here. All the loading logic for the third scene is here, so on so forth, so on so forth. So you can imagine this is like scene one, scene two, scene three. Whereas over here, it's like maybe scene two, and scene three logic all in one file or whatever. And that's fine to do for like quick prototype projects. But for other projects where you kind of just want to, you know, reduce your own cognitive load in sake of performance, I'll just, you know, make it a little bit more cleaner.

**46:55** · If I go to the code here, you can see that for my models, I have scene one, scene two, scene three. And each of them follow a very, very similar structure here. So scene one, I load the scene one GB. I load the scene one associated textures. And then use frame has all the animations that I do for scene one specifically. And then scene two is very similar. I load the scene 2 texture. I load the scene 2 GB file. And then I do the animations for scene 2 in inside this file.

**47:23** · You can see my other thing I also have here is a completely separate file for the panda. And it's also a completely separate GB file as well. And then the other one I have is a separate file for the moving objects. So like the bicycle, like the ship, like the camel, all this kind of stuff that is also all separated and baked together on a single texture or two textures. I think a single texture in in its own file. Do you have to do that? And the answer is absolutely no.

**47:53** · You could group moving objects and panda together into a single GB single texture single file as well.

**48:00** · or for each moving object like this camel could be part of scene 3 GB file and this skull could be part of scene 4 GB file and you could totally organize your code that way as well. This is just the way that I approached it because I wanted something where if in case I ever made a mistake it would be easy to fix and not too much abstraction and not too much optimization where I'll lose motivation and you know emphasis to continue like having fun is really important.

**48:28** · So if you're like overoptimizing and losing fund, you know, don't don't sacrifice that, you know, and lose your lose your side of your end goal. So at the end of the day, a lot of it is also just personal preference. So if I go back here and just take a look at the way I did my collections. Oh, sorry. Some leftover collections here cuz I started from like an old file, I think. Anyway, yeah, you can see I have like the first scene and then all the associated groupings that I have for the first scene of subolctions.

**48:56** · So I think for the first scene I had four textures there which was overkill but again I was just rushing and yeah you can see so forth. So feel free to skip ahead but for the ones that still want to watch me I will just show a little bit of that process right now. So now I'm going to move all the moving objects into a separate collection and those are going to be the ones that I bake together. Now when I say moving objects I don't mean like the scene moving ones. I just mean the ones that are traveling across the scene. So the basically the moving characters. Now, I don't have a main one like the panda one that goes throughout the entire scene.

### (Optional) Adjusting my scene for baking

**49:28** · So, I just have each character, you know, associated with each scene this time, but it's a if you have one that goes through the whole scene, you can have a separate one for that as well. Or you can just group it with these. I do have a lot of them paired to empties.

**49:42** · So, I'm just selecting the empty empties. And when I have all of those selected, I think I do. I can just hit period key to jump to one of them. Right click, select hierarchy. And it's just going to select all the children of all the empties that are selected. And I'm just going to hit M to make a new collection. And I'm just going to call this moving characters and create that.

**50:02** · I'm going to hit period key to jump to that. And then I'm just going to disable that. Now we don't see them anymore. Oh, by the way, you can get this Blender file on download if you want to follow along that way. You might have to replace some textures because some of these are I don't have commercial licenses for it. Um, but you you'll get the the Blender file regardless. All right. So, for larger objects like this one over here, which kind of covers the whole scene, I did split it up from that interior. If you didn't split it up, you might not have to join it or whatever.

**50:32** · You could do that as a completely separate texture itself, I think, or maybe two. I don't know. I think for simplicity purposes, I'm just going to split it up by scene. Now, if for some reason you do have accurate seams along where the divisions are, you can just hit L. And if you change this to UVs, it's going to select between your UV seams here. You can also switch in here to material. I think the default is seam. I'm not exactly sure. I think it's seam, but I'm going to select material.

**51:01** · And just be careful if anything else shares the same material as your background. It's going to select that as well. Here I am lucky in the sense that I only used it this material specifically for the background over here. So it's the same thing as if I just search for it. Hit select and you can see it's just going to select that.

**51:18** · I'm going to hit P separate by selection. So this is now removed from my my the rest of my stuff over here.

**51:26** · Now it seems like okay I have foreground felt here. So I'm actually just going to select this and oh that's also part of the group. So I messed up. So I'm going to se separate that by selection. And now I'm just going to Ctrl J and join those together. So now this look kind of looks like uh you know this kind of looks like maybe possibly one texture.

**51:48** · Okay. Same thing with these. I'm going to go into edit mode. I'm going to select this. I'm going to to select red BG and I'm going to hit P separate by selection. And oh okay. So now we have a we could just like crease those edges or what we have to do now is probably apply our modifier. So, I'm going to apply my scale. Nothing changed. Great. So, I'm going to F3, convert to mesh. I don't want to touch anything else yet because I want to know if uh, you know, I messed up anything along the way cuz I didn't check. If you know you didn't mess up anything, you can just hit A and convert everything to a mesh.

**52:18** · Just make sure you save a file in case you ever need to, you know, to fix something. I'm going to pepate my selection now. Okay, cool. And now it's working fine. And sorry, let me do Alt H just to bring this back over here. And I'm going to move this into a new collection. And I'm going to call this scene 4 mid autumn festival or whatever you want. Actually, I'll just call it mid because I'm too lazy to tag out the rest of it. So now I'm going to hit period key to jump there. Disable it. And then now I'm just going to select these and move them into scene formid as well.

**52:49** · Same thing with this over here. Okay, this one I have to apply the bevel modifier. I guess this time this one I'm not even using. So I'm just going to F3 convert to mesh here.

**53:01** · And I think that's too much bubble, but whatever. It's, you know, I'm too lazy to optimize that. So, we can do the same thing. I'm just going to hit select just to make sure that's that. I'm going to hit P separate by selection over there.

**53:13** · And I'm just going to move that into scene format. Cool. Now, I think uh we should just be able to go into wireframe. And I'm holding control just to deselect things I accidentally select. And I'm just going to select everything uh like so. We can apply all our modifiers and scale and all that later.

**53:31** · I'm going to deselect those lights. Just move this around. Make sure. Okay. So, I think that is everything in scene 3. Oh, I missed this right over here. Oh, that's also part of the lake. So, I need to fix that anyway. But let's go in here. Let's move that to scene for mid.

**53:44** · We can fix all the origin points and everything at a later time. Uh, this is also part of the teen cuddle. So, I'm going to do scene for mid there. And then this is something over here. Let's just hit control plus just to make sure we select everything. Okay. Yeah, it's nothing there. So, we can just piece over by selection. And then we can move that to scene format. And then let's just see. I do have something over here.

**54:04** · I don't know if that is far away or not.

**54:07** · So, let me just reopen it. Okay. It's part of the bunny. So, I need to move that into scene format as well. Cool.

**54:13** · Yeah, just make sure you don't miss anything and um you know, add it to that collection. I'm going to repeat the process with all the other scenes and I'll show what I'll do after I organize them all into their separate scenes. Oh, one more thing to note. When you start splitting your objects, it's going to name it into a separate object and your shrink wrap modifiers might no longer have their target. So, just make sure to apply your shrink wrap- before you start, you know, splitting stuff up.

**54:38** · If you can't add a loop cut or you can't inset and you have like these hidden faces that no one will ever see, you can just change your transformation point around the 3D cursor, select this vertex over here, shift S cursor to selected so it snaps over there. And then you can just select your ring over here and just hit S. And you can see that it's going to scale properly. And I'm just going to scale it in there. So we make it a little bit smaller. And yes, I will have to unwrap again because it's partly squashing the texture.

**55:06** · But that's just one way to reduce the amount of texture space. All right. So, as you can see, I have each scene in its own collection over here. And now I just want to go scene by scene and adjust origin points, delete extra faces, and unwrap and just pretty much prepare everything ready for baking. So, for this first scene, I don't think I will be baking anything that will be too much of an issue. This might be baked. Uh, let me fix this origin point real quick. I'm going to shift right click there, right click, set origin origin to 3D cursor. So now when I rotate it, it'll be fine.

**55:38** · Yeah, when I rotate this, it's going to leak a little bit of shadow here. I don't think anyone's going to notice. That's one of those ones that you can just bypass. But since this is so small, we should be able fine just to bake it a little bit.

**55:51** · The shadow will be off a little bit. If you want to, you can bake this background on a separate texture with this here and then bake this deer and this head on a separate texture on another time or the same texture depending on how you want to do it. I would just do it on two separate ones.

**56:07** · That way the shadow is in the right place. But honestly, just to save some time, I would probably just move this a little bit up. And who cares if the shadow is a little bit offset? Same thing here. I think during baking, I'm just not going to bake in the shadow at all. I don't even know if it has an influence. probably like a little bit.

**56:23** · So, these are going to be some moving objects that I will hide during baking.

**56:27** · Same thing with this one. This is a floating text box. I don't want shadow to interfere with anything. So, I'm just going to move it in the middle. Again, we have all that diffused lighting, so this isn't going to show anywhere in our scene. If you want to be safe, you can hide the rest of the items during baking, but I'm not going to. But, I can just tell from now that this isn't going to impact the lighting anywhere else in this scene. I think I'm also going to be rotating this fire. So, I'm going to split these up. If you want to, you can shifty duplicate it.

**56:52** · That way, when you're baking like this back, you still have the shadow there for the flame, whereas this is the flame that you're actually going to be baking in the diffused lighting. That way, you can rotate it and nothing will look a little bit off. Again, I feel like it's so small. This is probably one of those things that, yeah, even if you did bake the shadow and then rotate it and someone sees a little bit of that shadow, it's not that big of a deal. But I think like this occlusion, ambient occlusion going on a little bit back here. If you rotate this over here, it would look a lot darker on this side.

**57:24** · So I think that's more of an issue there, which is why I'm separating that out. So later, if you ever want to like reposition this one, you could like shift S, cursor to selected, select this, shift S, selection to cursor, keep offset, and then it'll just snap there.

**57:40** · Right. Now, just make sure to start looking for any things that look a little bit wonky because of a bad unwrap. Here you can see I was stretching some stuff here. I extruded here and I didn't unwrap. So, since everything is so flat, you can just go into use smart UV project and just scale it up and just make it look a little bit better. Yeah. Now, for some of these really, really small objects like this over here, I do use a black texture.

**58:09** · Well, let me actually turn this down.

**58:11** · Yeah, one is more than enough here. I do use a black paper texture, but honestly, you could just use a solid color and no one could tell the difference, but like because it's so small, it probably won't take much stuff on the texture itself.

**58:23** · So, I'm not going to bother changing that. But that is something you could also do if you wanted to spend time optimizing. Okay, so I think I moved out everything I need to moved out and double check things. So, it's definitely going to be a constant back and forth thing, but I think right now I can hit A to select everything and just convert to mesh. Right now, nothing seems to break, which is great. Let's apply our scale.

**58:44** · Yeah. Create. So, nothing has broken.

**58:46** · And now we can just start joining objects together that we're never going to like target or use or whatever. So, like all these objects, we can probably join them together. Just going to controll J. Origin point doesn't matter because I'm not animating this. Oh, looks like I did not fix this. Unwrap.

**59:03** · Actually, that stretch looks kind of good. But I'm just going to Ctrl L. Just select both of those. Unwrap those real quick. And yeah, that looks a lot better. But only join things that you know are going to share the same texture. I know I want all of this on one texture. Again, is it the most most optimal? And the answer is probably not.

**59:20** · But it doesn't matter because it makes semantic sense for me. So I think like by looking at this, I feel like this is going to be its own texture. So, I'm just going to right click over here, new collection over here. It will auto increment, which is really nice. And I think I'm just going to click and drag that here. I'm going to disable it so I don't see it. And I feel like this can also be part of that as well. So, I'm just going to click and drag that in here. Let's join a few more things that are going to be static and I'm never going to target them. So, definitely these.

**59:52** · I'm going to definitely join those. So, that'll be there. These I want to target later. So, I'm just going to go into wireframe and I'm going to join these here. Ctrl J. I'm going to leave these independent. Now, these trees, I think, are identical. So, this is one of those things where you only have to bake one of them. And then in code, you can just duplicate and move it there. Whereas during baking, you leave this here. That way, you have the shadow. I'm not going to do that because it adds probably like five or seven more minutes of work.

**1:00:22** · Should also mention if you accidentally join something and bake it together, you can always split it up later after baking and you you can always join objects after baking as well. Don't feel like you have to get everything perfect on the first run through. The benefit of joining them first is just for organization purposes and it's like one less object to bake which speeds up baking. So, as you can see, I just split it up into three collections. So, right now we have three textures for the winter scene. I did have this one here called temp pointer.

**1:00:53** · And these are all the objects that we aren't going to be baking, but we're just like using them for utilities. So, we're going to be deleting those later.

**1:01:01** · And here, if I just go over here and disable this one and just take a look at my winter 3 scene here, you can see I joined a lot of objects together. Like over here, some of them I might split up later. Like this mailbox. I'm definitely going to split this up later cuz when I hover it, I wanted to be able to adjust that. And I'll just order point. after baking, but during baking I'm joining them together. You could do the same thing with these. You could just join them together and just the origin point after you're done baking and separate them, but again, it doesn't really matter.

**1:01:31** · Now, one thing I do want to say here is we have three, but they don't seem balanced. The first one seems significantly going to take a lot more resolution than the other ones. So I think what I'm going to do is let's see select this and P separated by selection. I think is this also part?

**1:01:51** · Okay, this is also separate. So I think I'm just going to create a completely new selection. So I'm just going to move all this stuff into a new texture into a new collection called scene 1 winter 4.

**1:02:03** · So now right now this scene has four different textures. It might be overkill but you know better safe than sorry. And just from my experience, I know if we have 16, like four for each browser can handle that. And since these are all static, we can just probably just control J and join them all together.

**1:02:20** · Now, we are ready to start baking. So, as noted in the introduction, I am going to be using two paid add-ons, and I do expect you to already know how to bake as I did cover it in previous videos several times, but I'm still going to show you this anyway, just in case you want to get a little bit of a refresher.

**1:02:37** · So, the first thing I'm going to do is actually set up everything with a second UV map or third or whatever called simple bake and use that as the texture that we're going to be unwrapping to. In the past, I used to manually do it and copy and paste, but now I just use AI to generate me a script. So, I'm using Claude here, and you can see my prompt over here. Write me a Blender script, blah blah blah. It doesn't really matter how good your prompt is. And Gemini, Chat, GBT, all those work as well. Now notice I'm limiting it to just this collection.

### (Optional) Using AI to generate python script for Blender UV map creation

**1:03:07** · If you're confident in all your other collections as well, you can just do it for your whole entire scene.

**1:03:13** · That way you don't have to run the same script four different times. I'm just doing it one by one just because this is a tutorial. But usually I just do all my objects and finalize everything. So now we can just go to like the scripting tab, come over here, hit new, ctrl +v, and paste that in there. We can just hit alt p to run it. Or you can come over here and run that. But you can see shortcut is alt p. So now if I go back to layout and go through all these meshes, you can see that the simple bake is over here and it's al highlighted and ready to go for me. So now it's very very simple. All I have to do, let's just start from scene one winter over here. Let's just select this object.

### (Optional) Baking and unwraping tips with UVPackmaster and SimpleBake

**1:03:44** · Now there's only one year which is amazing.

**1:03:48** · And I'm just going to get rid of this dummy image there. It's just choosing one of the random ones. And since this is highlighted, we can just you and smart ue project over here. Take a look.

**1:03:57** · That is pretty good. Ideally, you'd want to straighten this, whatever, but I'm not going to waste time doing that. And we probably could fit a lot of other things on here, but whatever. It doesn't really matter. And I'm going to go on UV Pac-Man just like I just increase the precision just because I want to. And I'm going to enable pixel margin because there are times where I actually lower the margin.

**1:04:21** · Like ideally when it comes to 4K textures, you want to do a margin of 32 pixels. But sometimes I've done gotten away with 16 and I could like fit a lot more. So that's what I typically do, but whatever. It doesn't really matter as long as you don't have like anything overlapping or whatnot. So I think I'm just going to keep it 32 for this. And there are times where I turn on heristic search. It just spends a little bit more time to look for packing. And then we can just hit A to select everything. And uh Whoa. Okay. Something seems to be going on here.

**1:04:51** · When I hit A, it's also selecting this object. Why is that happening? Wait, let me see. I select this. Hit A. Oh, I think I might have accidentally selected that and went into edit mode. That's why hitting A was showing up there. So, okay, let me just uh Yeah. Okay. Now, it just shows this, which is what we want.

**1:05:09** · Come over here. U pack.

**1:05:12** · Same thing. And we just do pack and just let it do its job. It's waiting five seconds to find some stuff. And if it ever goes on too long, you can just hit ESC to cancel it. But anyway, this is fine. No one's really going to be looking at the distortion there. Um, same thing here. I think we could make those bigger, but I don't think it really matters too much. Yeah. So, that should be fine. Cool. And we can just do that for every single one. So, now we can come over here. Same thing.

**1:05:40** · We don't have to do anything here because it's already selected. Now, we just go into edit mode. U smart UV reject. And since it's all like basic, we should be fine just to take a look. And let's just do pack here.

**1:05:57** · All right. So now I think what we want to do is just look for areas that seemingly are too large. Even though they're a little larger face, I don't want them to have higher resolution. So what I'm going to do over here is turn on sync. And I'm just going to take a look at anything that might be a little bit too large for what it's worth. Oh, here is definitely Yeah. So, this is something that should not take up too much texture space because it's hidden by the snow.

**1:06:22** · Ideally, I feel like we should just use the snow and not even have this at all cuz it just takes a huge chunk. But, it's fine because in the event the camera angle goes here, I guess it looks a little more realistic.

**1:06:36** · Whatever. Anyway, this doesn't need need so much resolution. So, I'm going to scale that down significantly. I don't know what this face is. Is that the underside? Oh, no. It's just part Oh, it's just part of that. So, yeah, this bow should be scaled down pretty small.

**1:06:50** · Let's see. Do I have anything else?

**1:06:53** · Anything that I can scale up for to take more texture space, I can totally take as well. That one I'm just scaling down.

**1:06:59** · I don't know why I have two here cuz I think I deleted the back, right? I I I did delete the back. Oh, I accidentally used the solidify modifier. So, it's H.

**1:07:09** · Let's see. Will I ever see that is the question. At any camera angle, will I ever see it? I don't think so. So, this is the time where I probably should have checked this before doing anything, but I'm going to shift G. Select similar normal. Just turn this up a little bit.

**1:07:25** · Hopefully, it doesn't select anything else. Oh, actually, you know what?

**1:07:29** · Sorry. This should We should just uh leave it. Let's do Ctrl L just to select it. Ctrl I and just hide everything to make sure we don't select anything else.

**1:07:38** · And now we can just select shift G, select similar normal, and just turn it up until we select all the faces and just delete them.

**1:07:50** · Yeah, let's just make sure we aren't messing with anything. And let's just delete those faces. I don't know if we need that. Yeah, we can delete that. I know there's a little bit of extra ones, but again, it's also about your happiness. If it's taken away, you don't have to be perfect. As long as you get the most of it out there. So now that that's gone, I don't think we have to unwrap again. Here you can see the remaining phases. I don't think we have to unwrap again. We should just be able to repack now. So I'm going to alt h rehide everything.

**1:08:18** · And then you here you can see that underscore roof is still small. And I'm just going to hit esc.

**1:08:25** · Now the snowflakes I think are a little bit too large relative to the other things, but whatever. It doesn't really matter. Okay. So let's just double check. So, if I select this and this here, you can see now on the final texture, it's a lot smaller. All right, I think we have enough preparation. You can go with scene three and scene four as well, or you can just start baking now. I kind of always go back and forth, back and forth. Anyway, I'm just going to come over into scene one. I'm just going to come back over here. This is for later after we D noiseis, but I'm just going to change this to 4096.

**1:08:56** · You don't have to do that with symbol bake, I don't think so, but I just like to do it. which is better safe than sorry. And now with a symbol bake over here, I do have a lot of presets. That way I don't have to manually do it every single time. But for the purpose of this tutorial, I'll show it again. Even though I covered it in previous videos.

**1:09:17** · So I'm going to switch to cycles bake.

**1:09:19** · We want everything into a single texture. We don't care about the roughness and all that other sort of things because we're going to be avoiding real-time lighting. I think in future videos we're going to start working with some of those other maps in 3GS, but not this one. Cycles just bake everything into a single texture. We have scene one winter. I'm actually just going to name this right now. Scene winter one. And I'm just going to bake objects and add it to my bake objects list. Open up cycles bake over here.

**1:09:50** · Combined. I don't think we have to touch anything here. sRGB. I want to change this to linear rec. It's a pretty good looking color space with the Blender AGX. And if you're in a time crunch, you can also just d noiseise right over here. But I'm going to be using the compositor because I want to save it into a PNG later anyway. Nothing in special bakes texture settings. I'm going to bake at 4K and output at 4K.

**1:10:15** · There are times where you can bake at like 5K and output at 4K. That way you have a little bit more detail and can reduce it later. I've never needed to do that for a Blender web project, but you might have to do it for some other things. Here, this is the texture set for the name. We only have one object here, but we can just call it winter one or whatever you want to do it here. You can also see join B bake objects. So, like for this one over here, it would like join all these together as a single object.

**1:10:43** · We already did that beforehand, so we don't really have to touch anything. All 32 bit float. Multiple objects to one texture set. Again, that's for winter 3 scene, which I'll get to. BG background color doesn't really matter for us, so I'm just going to leave it as black. Export settings. I want to export my bakes. Navigate to whatever folder you want to do. And I'm doing open EXR, and we're going to convert that to a PNG later. So, basically EXR has a lot higher dynamic range of colors, so it'll save more information.

**1:11:12** · And then once we compress it to PNG, it'll lose some of that color data, but also still retain a little bit more than if we just just baked directly in PNG. Now, there's a lot of cases where you can just bake directly as PNG, and you wouldn't notice any sort of difference whatsoever, but I kind of want to be safe than sorry. So, for me, I'm going to be baking with a high dynamic range image and then later converting it to a PNG. It's the same idea as baking, you know, higher and then exporting lower except it's just with colors.

**1:11:43** · So for UV settings, we want to prefer existing UVs called simple bake, which is what we did over there.

**1:11:49** · Then for other settings, I want to copy objects and apply bakes. And now since we're working with alpha channel, well, I don't have an alpha channel for this one, but if you have an alpha channel, you should switch this to principal vsdf. You can always change that later, but I'm just going to keep it on principal vsdf. And then GPU if you have a better GPU. Now, if you are working with transparency like we were in the beginning with the panda, you can come here and turn down the alpha channel.

**1:12:13** · That way, you have transparency. I don't have transparency with this one. So, I'm just going to leave it completely at one, like so. And I actually think I'm going to change this to scene\_1.

**1:12:24** · And I'm just going to change this one to winter one. It doesn't really matter what you want to name it, but whatever.

**1:12:32** · And now we should just bake it. If you want to do backgrounds and still do stuff in Blender, you can do background.

**1:12:37** · It would take a little bit longer but less resources. I'm just going to do foreground. And just to check, if we go into edit mode, you can see this is the texture that we're going to be baking right now. And of course, don't forget to come over here and turn on face orientation just to make sure that the side that you want the lighting to be accurate on is going to be the one that's baked. So, you can do that with alt N and flip or recalculate outside.

### DON'T FORGET TO CHECK FOR FACE ORIENTATION/NORMALS BEFORE BAKING

**1:13:01** · Recalculate inside one of those. Hello, I am from the future. Now, notice how I am baking with just scene one active and not scene two and scene 4 or these other ones. Now, I actually made a mistake. I feel like I should be baking it with scene two and all these other ones active as well because a little bit of the red over here kind of leaks over.

### Back to baking stuff

**1:13:24** · Like, look really, really closely as I get rid of the fall one. You can see there's a little bit of shadow added and a little bit of ambience there. And these are the kind of details that I do want to keep. I feel like spring probably doesn't matter as much. Yeah, I don't think there's as much here. So, I think for most intended purposes, no one could probably tell. But ideally, if you're like splitting this, just make sure to realize that some of your other things might bleed up a little bit. So, so you'll see me baking only with this one active, but that is a mistake.

**1:13:54** · I should be baking with these other things active. And I'll show that correction a little bit later in the video. Cool. And here you can see it copied our object and applied the bake. Looks a little bit off right now. And that makes sense because it's hooked up to a principled VSDF. So if I go over here to the shader editor, you can see we have a double whammy. And the lighting is affecting it twice. So let's just click and drag that directly in there. And now you can see if we go in here what it would probably look like in the browser. And it looks pretty good actually. Wow. Okay.

**1:14:25** · Now let's just do one final check. And let's come over to compositing over here.

**1:14:32** · Click on new just to make sure. Let's mute this. Let's disconnect this. We don't want to see that stuff. And let's delete that. And let's search for an image over here. And navigate to our EXR file. So, navigate to our EXR file that we just baked over here. And let's change this to linear recre 709. Let's change this to D noiseis. Like so. Like so. And plug it in into the group output here. And of course, this time we do need the 4096. And now we can just hit F12. And now we can image save as. And now we can just save as PNG.

**1:15:04** · So I'm just going to call this save PNG. And we'll compress that later. Save as image. Now let's come back over here and let's just change this to the PNG version instead.

**1:15:18** · Nothing should change except the noise should be dinoised a little bit. Yeah, you can see the D noiseis definitely did a lot of damage to here. This might be one of the rare instances where you might not want to d noiseise, but I don't think it really matters too much here. You can see like yeah, with with the D noiseis, it's it's still fine as well. Okay, now it pays to be organized.

**1:15:42** · So, I'm just going to come over here and create a new collection.

**1:15:47** · Come over here, create a new collection, and I'm just going to do that. It'll automatically increment. And I'm just going to change that to underscorebaked.

**1:15:54** · I just realized we are missing the underline. Why is that? Oh, I probably had a space there. Just going to click and drag that in there. Now, we can just hide this one and rehide this one.

**1:16:06** · Sorry, I keep saying rehide. I mean unhide. Now, the reason I want to rehide the original one and not the baked one is cuz we want to bake with the properties that this one has rather than the one that the baked one has. For something like this with this kind of lighting, it probably doesn't matter if you bake with this one or this one. But just to be safe, then sorry. I'm just going to bake with this one. Now, we already got the shadow here. You can see this is the house. And I think either this or this is the little flame, this temporary flame.

**1:16:35** · So, we can actually just delete this entirely if if we wanted to. I know there is another shadow down here and possibly on these sides for the tab. So we can leave it in for the time being, but we got the main one that we need for there. So we could just delete it. So yeah, everything is the same exact process. I'm just going to go into scene two now. Well, actually, let's just do scene three cuz it's it's got more than one object. Same exact thing. We already set this up.

**1:17:02** · Simple bake is all selected. Do our script. Go into edit mode. A select everything. Smart UV project. Make sure I think we I already mentioned it but you know make sure to apply your scale and everything is scaled. One I think I did mention that earlier but just just to say that again now we just pack it hit ESC. If there's anything that's taking up too much space we want to get rid of it. So let's see. Yeah, this is taking up too much resolution. So we can make that a little bit smaller.

**1:17:31** · Yeah, I don't think there's too much on this one. So we should be fine. I'm just going to repack it again real quick and we should be good to bake. So, let's go back to render and let's just clear this out and add it all here. So, those are all our objects. I feel like I could join a lot of these together, but whatever. It doesn't really matter. And I'm just going to change this to scene.

**1:17:54** · Well, actually scene one is fine. I'm just going to change this to winter 2.

**1:17:58** · Well, actually, sorry, this is winter 3.

**1:18:00** · So, I'm going to change that to 1, two, three. And we don't have to touch anything else. We're good to go. And just headbake. All right. So now that is done. You can see we have all our stuff here. I probably should have named that better, but let's just move that into scene one as well. And here is when we can actually start repositioning these.

**1:18:15** · So we can come over here. Cursor two selected.

**1:18:19** · Shift select this one. Shift S, selection to cursor cube offset. Whoops, I accidentally select this. Shift S, selection to cursor cube offsets. Well, now it's probably time to just like turn off the one that's overlapping. So it's probably this one. Yeah. Shift S selection to cursor and then this one as well. And again, we can preview it by directly putting it up there. And it seems fine. Yeah, it looks nice. And being organized pays off. So, I'm going to hold shift and select this. Control shift over here.

**1:18:49** · Hold control, select this. Control shift, select this over here. Move it into a new collection. And I'm just going to give it that name. But I'm just going to copy and paste this like here. This is going to be scene three. And I hopefully you watched the future correction video where I did not bake with these. So now I'm gonna for the rest of them I'm going to bake with those active and I'm going to re-ake winter 3 and winter one. And yeah, I'll have to move the flames again, but whatever. And I'm just going to repeat this process. And you can do that for your scene.

### (Optional) Asset preparation after done baking for development.

**1:19:21** · And I'll show you some of the more quoteunquote special bakes or like special preparations that you might need to do later. Another tip, by the way, symbol bake will hide your original objects if you have that setting on.

**1:19:34** · Instead of like going back and clicking and dragging and unhiding all of them like that, you can just click this and click it again and it'll completely reset all the hidden states. You can also write a script to do that as well, but this is just faster. So, just another few tips and tricks. When you have a lot of text like this, just use a image instead rather than actual text.

**1:19:55** · So, these are all just images that I exported here. Here you can see I just mapped an image onto a subdivided plane and then just shrink wrap out of her.

**1:20:03** · That way when you unwrap and pack with UI Packmaster, it's not going to add 32 pixels between like each letter and that will like clog up the the entire thing.

**1:20:12** · Now there's ways to pin it where it takes a certain amount and you can just do that and repack it that way, but that just takes more time than just typing out the text in another software and uploading an image that way instead.

**1:20:23** · Now, I will also say when you bake it after and hook up the alpha channel and everything, you might still see like this full black thing here though, but don't worry about it because that's not how it actually looks when you export it into the browser. And you also don't have to worry about hooking up anything here because we're going to be loading it separately in the code rather than keeping it embedded. So, I also just want to show you how I organized everything. You can see that I have the scene one winter and then all the other ones. I didn't use any temps for any of the other ones because I didn't want to invest time on it and I could live without the shadow.

**1:20:53** · So that was just for demonstrations of this tutorial and but you can see that it's pretty much the same thing. Every category over here gets a collection over here as well. All right, so let's move on and talk about the moving characters. So I'm going to hide all this stuff. Whoops. I'm going to hide all this and let's talk about the moving characters. All right, so let's take a look about some of the thought process that I had with the moving characters. Now, all these moving characters are positioned within the scene, but it doesn't really matter where you bake them, as long as the lighting is uniform around them.

**1:21:22** · So, unless you're far out to the edge, the lighting will be uniform, whether you're in the center or at the edges there. So, it doesn't really matter where you bake.

**1:21:31** · So, let's just get rid of all the noise and take a look at the moving characters and some of the thoughts that I had here. So, when I'm scrolling, I want this to pivot and rotate. So, because it's going to do that, it might have a shadow here if I let it block by the clothes, which is why I separated it from the clothes over here and so on so forth. This one is going to be I think I will also be moving that. So, I'm going to select these. I'm going to be separated by loose parts and I'm just going to Ctrl + J to join these. And all these or all these messed up origin points I'll fix after the baking.

**1:22:02** · You can fix it before if you want, but I'm just going to bake it after. If you want to extend these arms, I guess you could also, you know, if you wanted to split those up, you don't have to be separated by selection if you didn't want to. I just did because I will for these arms.

**1:22:18** · They would be separate eventually anyway. But you could leave it here and just move it out in edit mode. Kind of just what I did here. You can see it's the same object, but I separated out.

**1:22:26** · That's only if you want to move that the hand. I don't think I'm ever going to move the hand. And even if it does, a little bit shadow there is probably not too much of a big deal. So, same thing with the head. I don't want the head. I might move it slightly. So, there might be a slight shadow there. If it doesn't bother you, don't even worry about it.

**1:22:43** · Don't even worry about moving this stuff out. But if it does, you can totally separate that out as well. You'll also notice that each one of these probably should have their own stick. And you're completely right. But because each stick is identical, and yes, the shadow might be slightly different on any of them, no one's going to be paying attention. So, we can actually delete these extra poles if you want to keep them temporary. So you can just like select and snap to them later. You can totally do that. But I'm just going to delete them and I'm just going to bake with a single pole.

**1:23:11** · Now I do want that shadow there, I think. Yeah, let me just confirm that. I think I want that shadow there cuz it'll show. Yeah, we still have that shadow there because it's being blocked by the character itself. So every stick will have that shadow in there. It might look a little bit off if you play close attention depending on which one it is, but you know, at the end of the day, it's probably not going to really matter too much. So, I think I might move this a little bit here, too, just so we get a little bit of shadow there. Now, you might be saying, "Well, the body also gives some sort of shadow. Shouldn't we move it over there?"

**1:23:42** · And you're totally right. You could totally just bake it like that if you wanted to. But the thing is, it's also going to be hidden, so no one's really going to notice anyway. So, I'm just going to leave it out here, but if you want to, you can move it closer and make it like that.

**1:23:56** · Okay. Now, I just want to talk about some of the more common ways to animate a 2D face. I think one of the most common ways and one that I was thinking of is using a texture map. And basically in code, you just offset the UV a constant amount and it'll switch between them. In Blender, there's a lot of tutorials showing you how you can do this with a node setup. And this is this is a very common way to animate the face.

**1:24:19** · Now, I'm not doing that because I only have two states that are going to be shared across my face, which is the default one over here and the smiling one right over here. Now, this one is specific to this face over here. So, this isn't going to be a default one, but this one will be. And the default face I already split up here. So, this one, this face over here is going to be shared across all the other ones. Maybe I'll move it out a little bit just to make sure nothing is affecting anything.

**1:24:48** · So, I can actually start deleting these because I already have the default face copied to the other face. If you want to keep that just for reference, you can totally do that. And I don't need that cuz that's also part of the default face. Same thing with this face over here. This is going to be shared across this character and this character. So, I'm splitting them up. Same thing over here. Let me join these together. This is the character. Sorry, I think I might have Yeah, I might have just really repositioned that somewhere else.

**1:25:17** · But you can see this going to be shared across this face and this face as well.

**1:25:24** · So, because I only have two states, it's just easier just to bake the states and switch between meshes rather than creating an image texture and UV offsetting between two face states. In my next video though, I do actually plan to cover this one. So that's another reason why I'm not doing it in this video, just cuz it would add a little bit of more time. The last reason I'm not doing that is so I have some perception of depth.

**1:25:47** · So if I show you on this face here, you can see because it's got the paper, you can I can deform it a little bit and give it some a little bit of depth. I think from far away, no one probably can tell, but you know, it's just a little bit more realistic that way. Now you can totally, you know, when you map your face to the plane, you can subdivide it a bunch and then give it depth that way by like bending stuff along your subdivided plane, right? And everything in between would be like alpha transparency. You could totally do it that way as well, but I just did it this way.

**1:26:19** · So I'm just going to keep it that way. So those are kind of like the three reasons why I'm not using this very very common approach to animate instead. For the record, I should also mention it's not just about the face, right? Like you can all these body parts and these head shapes and all the accessories too like the hat. They're all kind of like within reason to use just separate planes for it.

**1:26:39** · So you could have like one plane for the hat here, one plane for this back hair over here, one plane for this one, one plane for this one, one plane over here, and you would just switch, you know, offset the UV to switch outfits. So you don't actually even need like this arm is identical to this arm. So actually you could just delete this one and then instance it over on the other side if you want to go even further optimization. Same thing with the foot over here. This could just be a plane over here and you just instance that plane or mirror that plane over onto the other side.

**1:27:10** · Same thing with this back hair which is front and then another front for the front part of the hair. So like you could just use a bunch of planes instead of the actual meshes itself. So in that case, what you do is right, you'd make the meshes first or you know in your illustrative software wherever and since doing in Blender you

**1:27:30** · just orthographic camera and render this transparent background image here and then you just keep doing that with all your hairstyles and then put it in a grid and then you could just use a single plane here and swap between all those rendered images that you put into a grid. But yeah, I'm not going to do that just because I want to save time.

**1:27:46** · But if you want to be scalable, definitely go with that approach. So now you can see that I have everything baked and now it's just the time to start organizing things in every single thing.

**1:27:55** · So I'll just select this shift s shift right click somewhere shift s selection to cursor and you know just adjust it back to where they used to be. I'm not going to bother with instancing even though it's got better code. But yeah, I'm just going to shift duplicate that and find my other character right shift s selection cursor. Keep offset rotate it. You know what I'm doing? GZZ. Snap it over there. RZ. I know there's like a line rotation to target snapping stuff and that all like over here and whatnot, but honestly, it doesn't really matter.

**1:28:27** · Just having it a little bit whatchamacallit like um just having it like a little bit off anyway makes it a little bit more realistic cuz paper bends. And if you want to adjust one, you can totally do that after, right?

**1:28:39** · Because it might not be too distorted, right? So it from far away, you know, maybe no one will notice those details, but you can totally do those details if you want to. But yeah, I'm just reorienting everything back onto the faces. Cool. And I'm just reorganizing everything so I don't have to do it later.

**1:28:58** · And whoops, I forgot to join these together, so I was just wasting my time because Whoops. You see? Well, let me see. Just move it down right back to where it used to be. Cool. Super super cool.

**1:29:11** · And if you want to move some stuff in front and some stuff behind, you can totally do that as well. So, you know, you don't have to limit yourself. Well, let me just go wireframe.

**1:29:21** · Yeah. And that's pretty much all I'm doing now. Same thing with the stick here. I can just duplicate these. Shift C. And just move them across all my objects over here. And that's all I'm doing. So, keep the ones that you want separate separate. And the ones that you want to animate later, you can keep them separate as well. If it helps, you can parent them to an empty, but I'm not going to be doing that yet. I also renamed them so I can identify them a little bit later. So, your naming convention is up to you. It's just however you want to do it in your brain.

**1:29:53** · Like some of them I used the collection name and then underscore and others I was just too lazy to copy and paste it again, so I didn't bother. But yeah, so I just did that. And if you want to use your existing meshes to create new ones, you can totally do that as well. Like let's say this one over here, I just added in the loop cut. Shift D P separated by selection Q origin geometry. Let's just go back here and hold alt and let's just get rid of the loop that we created there.

**1:30:22** · And yeah, now we can just use this in our scene if we want to adjust something somewhere, you know. So back to dnoising the textures. I just want to give out a community shout out for this tip and trick that I haven't shown in previous videos. But if the dinoising is a little bit too strong, you can mix it with the original image a little bit and control the D noiseis that way. The whole idea is if the D noiseis is too strong by default, you can mix it a little bit with the original one and control the D noiseis that way.

**1:30:52** · That way you can get a little bit rid of the noise but not too much. Yeah, but just play around with it. It really depends on your textures and stuff like that. All right. So, I have all my textures here and as you can see, all of them are over 20 megabytes and all of them are 4K images and that would take forever to load in the browser. Even if it would work, it might crash some devices. So, we have to compress. Now, I did cover a lot of compression tools in previous videos and a lot of them are still valid, but I just want to talk about two new ones.

### (Optional) Online optimizers and texture compression tools

**1:31:22** · If you want to hook it up and export it embedded in the model, you you can use some of these online tools. So here, let me just upload this one to Simon Dev, who is a very famous 3GS YouTuber. If you know me, you probably know him. Uh, as well, he's got like 300,000 subscribers or 200,000, I think, or 400 now. I don't remember. Mainly, we're aiming for the texture here. You can set, you know, the max resolution. So, this will rescale. It's pretty much just like just like what we did when baking.

**1:31:53** · You could like bake at 4K and then output at 2040. So, it'll just rescale it, right? like like here pretty much if you just baked it like that that would have been the same thing. And then sorry I cut out the video but then you have your compression methods here like basis and the more typical ones. Each of these do have their specific use case but I'm going to be going for basis because it's typically what we consider optimized most for the GPU.

**1:32:20** · And here you can see when I applied that it changed the file size from 32.21 21 megabytes to 747. And here you can see when I downloaded 748 kilobytes or kilobytes kilobytes. Of course, it is significantly smaller, but we also want to check just to make sure that it looks fine. Now, here you can see some issue with the text over here.

**1:32:43** · It's having a little bit of issue. When I get closer, it's fine. It seems it's like it's okay. This might be resolvable in a code setting like with alpha tests and whatnot. So, I'm not exactly sure yet. And the wall itself actually looks pretty good. You know, even at 2K, it's a little bit more blurry, but we're going to be far away. So, we're like about here, so it might be fine. Now, there is some lighting on it, which is why it looks a little bit off. But from my experience, this is actually not so bad. But yeah, it's pretty much just trial and error.

**1:33:13** · And then this one is made by Shopify, and it's very similar to Simon Devs. You have, you know, your options here like basis, webp, so on and so forth, compression, and all that.

**1:33:22** · Now, there are a lot of other bulk command tools online that are free to use, I think, where they'll resize all your images, uploads, but I think we have so many that we'll probably have to enter a paid plan. So, instead, this time, I'm actually going to use this one. Last time I said I wasn't going to use it because I was going to do it the beginner way, but this time I'm actually going to use Image Magic, the developer way. That's a very popular thing to do.

### (Optional) AI PowerShell/Bash Script and ImageMagick

**1:33:48** · just install it for your device and then open your command prompt and just type magic- version just to make sure oops sorry magic- version just to see that it's installed and indeed it is now we can just copy our path over here cd to

**1:34:04** · navigate over there and now we can just rescale all our images in bulk so it might take a little bit of a while but it doesn't really matter so I'm going to make deer a new directory and I'm just going to call this rescaled but call it whatever you want and then now I'll do magic and modrify- path. And we're going to set it to rescaled the new folder that we just created over here. So, every image that it rescales, it's going to put it into that new folder. And then we're going to use the resize command and we're going to do 20480 by 20480. And then all that ends in PNG.

**1:34:35** · So, everything in this directory that ends in PNG star is all, right? Like import all from 33. Same thing over here. And we're just going to hit enter. And we're going to wait for that. And if I go in rescaled, you can see periodically it's going to start showing up the 2K textures over here. If I right click on one of these and go into properties, like over here, you can see that just by reducing it to 20480, it chopped it down by about 75% or 70%.

**1:35:07** · And now you can see dimensions are 20480. And wow, it's done in about 2 or 3 minutes. So obviously that's going to depend on your device, but yeah. So, the next tool that I'm going to be using is KTX software. I I think I used it in the past, but yeah, just make sure to redownload it if you need to or download if you don't. You scroll down a little bit and just look for the one that you need. I'm going to be using this one cuz I'm on Windows, but you know, find the one that you need. So, once you have this installed, you can run these on each single one of them.

**1:35:37** · So, this is going to be the new name, and then this is the one that you are named for your image. I don't really know what else to say here other than it really depends on what scene and how much you're willing to sacrifice and whatnot, but typically for something like what I'm going for, I go for the highest quality ET1S. And this is the command that you put into your command prompt. Again, just play around with the setting. It's really, really up to your scene and your value system. You may be asking, Andrew, do I have to do that for every single one individually? That sounds painful, man.

**1:36:10** · I've got so many. And the answer is of course not. And this is the first time I'll say use AI to help you here. So I have AI to help me generate a script that runs on PowerShell that will use both the tools that I installed, both KTX and Magic. First to resize it and then also to convert it to K2X, all of those in that folder. So we can do exactly what it wants us to do. Let's just give that a copy. Let's come to our paper textures. Let's create a new file over here, just a text document.

**1:36:43** · And let's just paste that code that it gave us and save it. And now it's telling us to save it as a PS1 file. So, PowerShell file. So, why don't we do that? Let's rightclick and let's rename it just like so. Hit A to select everything, including thetXX. And we can just ignore that warning. Super cool. And all we have to do now is rightclick and run with PowerShell. So, let's just take a look and see what it did. Okay, it's working. It's running the 2K PNGs.

**1:37:10** · And maybe right after we'll see a look at the final KTX as well. And now you can see all these just finished and it just printed out converting to KTX2. So let's take a look. And oh my gosh, it is working its butt off right now. Now converting to KTX2 takes a little bit of more time. So it really depends on your computer. Wow. Now you can see it's only 73. And voila, in a few minutes, we did all that while we were just like dancing in our room and stuff. And we can just like check it now.

**1:37:41** · So, we can just like upload it to like an online viewer just to see how it looks. And it actually doesn't look too bad at all. Now, you might have to play some trial and error, but whatever. And I'm just going to post that command here if you want to use this one, but literally any AI can generate you script for you want. And you can use whatever command you want.

**1:37:59** · Just change it to whatever works for you. Now, this is PowerShell. So, if you're on Mac, a Mac device, you can use an equivalent like Bash just to ask the AI to translate it over to uh like ZSH or something like that. So, now that we have all the textures ready and compressed, now we need to export our stuff as GB files. So, in my Civo bake, I have five collections, which means I'm probably going to export five GB files.

**1:38:24** · Now, it really depends up to you and how you want to work, but for this scene, I think I'm going to do five GB files, one for each scene, and then one for the moving characters. Now, I did say naming conventions are great, and I did try doing that, but you know, I was getting really, really bummed out having to copy and paste it each time and change the number. So, instead, I went to my friendly AI over here and just type this prompt over here about like 2 minutes of typing. But basically, the idea is for every collection over here, I just take the prefix my baked and attach it as a prefix to the mesh object if it exists.

### (Optional) AI generated Blender scripting for naming conventions

**1:38:58** · Now, some of these I manually copied and pasted, but I regret doing that because that was a waste of time. And here, it generated me a script for that. So, I'm not even going to bother checking it.

**1:39:06** · I'm just going to copy that. Go into my scripting tab here. And I'm just going to paste that. While we could create a new one to not override the other one, but whatever. And now, we just got to change the name over here to the one that we are. And hopefully this works.

**1:39:19** · And of course, it doesn't work. So, what did I do? I asked my buddy, "Hey, it's not doing anything, bro. Are you sure it checks the children inside the parent collections? Cuz that seems kind of sus.

**1:39:30** · And of course, it is using recursion, of course, right? So, what are we going to do? Well, we're just going to copy and paste that right over there. And we're going to copy and paste this this new script over here, just like so. And then we're going to get rid of that. And we're going to hit alt P to run. And wow. Okay, now it seems to be working.

**1:39:48** · Thank you, my AI. Let's just make sure that it's all good. Yes, and indeed it does seem to work. This is redundant because I hit it as what's the opposite of prefix? I don't actually know. But for all of them, it does seem to work.

**1:40:02** · If you want to use this, you can totally use this. Just rename it to whatever collection that you want. Again, like even even the naming convention itself for the collections, you can actually prompt a script to do that for you. That way, you don't have to manually type one, copy and paste two, and three in. I I I should have done that earlier, but whatever. It doesn't really matter. in in in any case if you want to use it, it's here. But if you can use Chad GBT, Grock, Claude, Gemini, whatever it it it can handle this stuff pretty equivalent.

**1:40:32** · It's like really just basic Python here.

**1:40:33** · All right. Now, we can start exporting.

### (Optional) Exporting GLB Files

**1:40:35** · So, I'm going to rightclick and select objects and it will select everything and all the sub collections and everything as well. We can come over here, file, export, glTF. And we want to remember export settings. That way, we don't have to change every time. only limited to our selected objects, the ones over here. Transform, that's just adjust for the axes on export. We don't have shape keys, but if you do, you can leave that on. And if you do leave it on, I think our transformation tool will get rid of that information if you don't have any.

**1:41:05** · Anyway, so whether you leave it on or on, it doesn't really matter.

**1:41:09** · For materials though, we don't want to export them. I think by default it exports. We don't want to export them because we have those separately and we're going to reattach them in code and we don't need skinning because we don't have armatures and bones and stuff like that. I might come back later and add those in. Like I might come back later in the video and add some shape keys and skinning but for now you can uncheck those if you want to. We don't have any animations so you can uncheck that too.

**1:41:31** · I might come back and later in this video and add some animations too. So now I do want to comment on compression here. Now, I did show in previous videos a lot of compression tools and compression methods and as well as the other online ones that I showed you. For most projects, I guess it doesn't really matter whether you use the one built into Blender or an online tool or command line tool. I would only consider like the special compression methods or trial and erroring if you really really need it. But for most projects, it doesn't really matter if you use the Blender compression one or the command line tool.

**1:42:02** · Again though, for us, it doesn't really matter because the command line tool will apply the same compression anyway. So, you can leave it on or off here. It doesn't really matter. And make sure to change the name to the prefix of your collection. This is going to help us with scripting a little bit later. It's totally optional, but I'm just going to do this because it's a little bit faster.

**1:42:25** · So, let's just upload it to a viewer.

**1:42:28** · And yeah, so we got everything that we needed here. All right. So now what we should have is all our KJX files and then all our GB files. So I have 1 2 3 4 5 GB files over here. Now we're going to process them in a little bit, but for now let's first start with the code. So of course navigate to wherever you want to create a project. And I'm just going to go there. I usually start with a boiler plate. I'm not going to start with a boiler plate cuz I want to appeal to the vibe codests and talk about architecture a little bit before I get into the code.

**1:42:58** · So feel free to skip the setup if you don't need that. All right.

### (Optional) FOR VIBE CODERS - basic coding setup

**1:43:02** · So to for the vibe coders out there, if you're ever wondering why we're using the tools that we're using, I think it's very good that AI actually helps fairly accurately here. Like I did a pretty poor prompt here, but it actually gave a pretty decent answer here. So the first thing we need is a bundler. And a bundler just takes all our development tools and compiles it down to what the browser actually supports. because the browser doesn't support SCSS. That's not what shows up on the web page is that SCSS compiles down to CSS at the end of the day.

**1:43:34** · You might have heard Tailwind CSS that also compiles down to regular CSS at the end of the day. And that's what bundlers do. They basically take all our development stuff, optimize it in a various different kinds of ways and output it into HTML, CSS, and JavaScript, which the browser can actually handle. This is like web assembly and let's just keep it simple for now and say that everything compiles down to HTML, CSS, and JavaScript. So, how do we actually even use Vit? Well, we need another tool like Node.js, which is basically lets you run JavaScript on your local device instead of in the browser.

**1:44:06** · And very similar to how there's different versions of Blender, and some Blender plugins only work with specific versions of Blender. That's kind of the same when it comes to packages and Node.js. Some of your projects you actually want to remain in a older version of Node.js and work with like some of the packages that haven't been updated yet in a lower version of Node.js. And the way to management manage different versions of Node.js unlike Blender where you can just like download different versions and open those.

**1:44:36** · Quickly use a tool like Homebrew and install Node with Homebrew and then you can switch between your Node versions like this. I'm not going to do that because that's not necessary for this video. Okay, let's go back. If you want, you can do node-v just to check the version. Here I have the latest version installed.

**1:44:55** · If you're on an early version, it doesn't really matter. And now we can just get started over here. So we're going to create a boiler plate project just right over there. I'm just going to hit enter. Default is Y. I'm going to call this Amy Leo. It's really up to you though. And I'm going to select React because we're going to be using React 3 fiber. I'm not going to use TypeScript for this project. I'm just going to do regular JavaScript. I'm just going to hit no on V8 beta. And we'll just hit yes to install with npm. And sweet. It actually already started.

**1:45:24** · We can hold control and click on that to see our local server. That's not what we want.

**1:45:30** · Let's do control C or command C if you're on Mac. Let's do CD to Amy's paper portfolio. So, this enters the directory that we created over here. And then we can just do code dot and it should open up in VS Code. And indeed it does. Super super cool. Again, that's right there.

**1:45:48** · We just created this. All right, let me zoom in here for the vibe coders and just take a quick screenshot. So basically what we have here, node modules, once you install like 3GS and other sorts of stuff, it all goes into node modules over here. So all your packages and everything. So like 3GS like this is just like some code that someone else wrote, right? And we're just using it. it's putting in there.

**1:46:12** · Public is where our static assets go, like images, our models, and so on so forth. You can all change this in a config file over here if you want to, but we're not going to be touching that.

**1:46:21** · And then source is pretty much where all your coding logic goes. These other things you don't really have to know.

**1:46:25** · Git ignore just like prevents you uploading like huge things to the GitHub repository like node modules. And basically these packages, they tell you when you run npmi install what packages you need and then it generates this over there. So it actually does that in the browser when you build build and deploy.

**1:46:43** · Read me is just read it. ESLint it does things like check for unused imports, check for formatting things. We're not going to be worrying about that whatsoever here. So that's irrelevant.

**1:46:53** · And then index html is your actual web page itself. So even if you're vibe coder, you can look up what HTML is, but it's basically the page. And then CSS is the styles and then JavaScript is like the brains of the whole thing. Now I also want to cover the concept between an MPA and an SPA for the vibe coders out there. So MPA stands for multi-page application and SPA stands for single page application. That does not mean if you have multiple pages, it can't be a single page application. So let me explain that real quickly.

### (Optional) FOR VIBE CODERS - multi-page vs single-page applications

**1:47:21** · When it comes to a multi-page application, every time you navigate to a different page, it'll trigger a complete browser refresh and load another HTML file. When it comes to single page applications, you basically have like these the JavaScript running the show pretty much. So instead of switching HTML files, you just switch the content within the HTML.

**1:47:42** · So let's say you have like a component over here, like a container over here, instead of switching to an entire new component, sorry, another new in index.html HTML file with new components. Instead of doing this, which is what a multiplayage application will do, it'll actually just take all that content, toss it out the window, and then a new fresh of HTML content will be attached inside here instead.

**1:48:08** · So, as you can imagine, single page applications are significantly more popular with 3D experiences because it's easier to like, let's say you have your 3GS canvas, right, as an HTML element.

**1:48:19** · you can keep it on the page and then you'd play some fancy transition and something and have it listen to that state while you swap out the HTML content or some other sort of content.

**1:48:29** · That's a lot more difficult in multi-page applications. There's a lot more nuance there other than I just wanted to say that React is going to be a single page application for what we're doing. So I do want to show you a very popular website over here. You can see take a look at this refresh button here.

**1:48:44** · As I navigate to another page, you can see it actually doesn't refresh, right? Let me show you that one more time. It doesn't actually refresh. And if you take a look at the content over here, you can see a lot of things stay the same. They just change like their state. So, they're not being replaced or anything, right? So, this is a clear example of a single page application.

**1:49:04** · There's also a lot of pros and cons between why you'd want to use one over the other. And a lot of websites that you visit do use actually both for different parts of their website. Like MPA just logically, even if you know nothing about coding, you probably know that it's better for SEO because you have like more files that the web will scrape and things like that, right? So that's why you might use MPA over SPA.

**1:49:28** · There's a lot of other reasons and details, but whatever. We're not going to really bother with that other than yeah, we're going to be working with an SPA here. So just to show you an example of a multi-page application though here as I can see take a look at everything here as I switch the refresh button is going to trigger and everything over here updates and that's unlike the Lando Norris thing where we saw a lot of thing you know we

**1:49:51** · didn't see it flashed just states were changing not every single thing again a lot of websites use a combination of MPA and SPA depending on what they need but that was just an example so I did cover a little bit of architecture earlier but I just want to kind of finalize that that comment. Now, of course, architecture at the end of the day depends on you, but I do just want to explain why I'm taking the approach that I'm taking. The first thing I like to do is not think of coding architecture any different from real life architecture.

### (Optional) FOR VIBE CODERS/NEWER DEVS - project architecture explanation

**1:50:19** · Like, let's say you own a photo studio.

**1:50:21** · It's very very similar to Blender in the sense that this is your studio. Like, this entire thing you're seeing right now is like your building studio just in a 3D environment. And when you add an object like this, this becomes like your lighting object or your chair that you're modeling or your character, right? You can think of all of these objects like components. And then let's say you have like another object over here. And you parent that like control P there. So now when I move this, it's like this. And now there's like this sort of hierarchy. So you have a child component and then you have a parent component.

**1:50:52** · And then you have your little scene over here, which you can consider these cubes as your scene. And the whole entire thing, your collection is like your entire experience. Scene collection might be like your entire building and whatnot. So that might not be clear at the moment, but trust me, it will get a little bit more clear as we dive into the code. So let me just show you that in my Panda one here. So I have the experience. As you can imagine, that's like your scene collection in Blender, your entire thing. And then you have your components like your cubes and models and things like that.

**1:51:20** · I only put a curve in here cuz I have a separate one for models, but models could also be part of components. But yeah, like when you add a cube in Blender, you can just like imagine you add cube.jsx here in code. Hooks is you can just think of reusable functions. So basically scripts in Blender are like hooks in code.

**1:51:38** · That's a little far stretched, but that's kind of like the idea. And utils are you can also think of those just like functions like Blender scripts and and things like that as well. I guess a better way to say hooks in is like node groups in Blender. when you create node groups and reusable node groups that's kind of like what hooks are in code. Now there are components over here outside the experience. These are the HTML and CSS components. So like the user interface components. So these are the components for the scene and then these are the components for the HTML and CSS user interface components.

**1:52:08** · Then app.jsx is your user interface and your 3D experience. So you can imagine app as Blender and then index.html HTML I guess is like kind of your computer but it points to main.jsx which is has a few other things but basically injects your app into your index.html file which gets displayed. So you can think of index.html like blender itself or main.jsx as blender itself or app.jsx as blender itself.

**1:52:37** · But basically all your coding logic injects into app.tjsx injects into main.jsx index.html attaches to main.jsx. jsx. Now, you might be wondering, Andrew, why do you have app over here if main is the one that actually injects everything? Like, what's the point of having app.jsx? Why did they give us an app jsx when you could just do this? Well, for this kind of project, it doesn't really matter if you want to do it this way and get rid of app.jsx entirely.

**1:53:07** · But when it comes to more scalable applications, you'll see why app.jsx comes into play. A lot about about it is maintainability and readability. But yes, if you wanted to get rid of app.jsx, you could totally do that for this project. But that's typically not what people do. So here you can see it just kind of makes a little bit more semantic sense to a reader. It's like, okay, there's nothing else besides this current app. So that's why if you take a look at the boiler plate, they also gave the same exact structure here.

**1:53:36** · Again, for us, it doesn't matter, but that's just why they gave it to us. And really, at the end of the day, it's kind of up to you how you want to organize things. You could also put the, you know, the UI components as part of the experience components because arguably UI components are also part of the experience. So, it's really up to you and how you want to organize things. And if it helps like you can create another one here called app and then place both these and rename this to like user interface and then place that in there. Like it it doesn't really matter for these kinds of projects.

**1:54:06** · Now, different frameworks like next.js, JS they have like nesting things and patterns that you can can adhere to for what we're going for we are very flexible when it comes to architecture.

**1:54:18** · So let's just get started now and just to show you one last time we have our app over here. Scene collection is like our index.html file. So we have our app and we have our experience which is what I'm going to start off as the first file. Then we have our scene over here.

**1:54:34** · So this is like the stage and experience is like our entire building. And then we have our component cubes over here which I renamed. And then we have like our subcomponents over inside over here.

**1:54:43** · Okay. So just to save myself some time, I'm going to copy both these folders over. You can totally do that if you want to. We're going to delete everything inside. So I'm just going to delete both of these. And experience.

### (Optional) FOR NEWER DEVS - Basic coding setup - see commit to bypass time

**1:54:54** · I'm just going to delete all the files inside, but keep the names here. So just going to delete those. If you don't want to copy and paste, you can just rightclick and create a new folder, of course. But I'm just going to start from scratch. So, let me just delete those as well. So, of course, the first thing we need is experience.jsx like so. Right, let's type R Ace just to create a quick component. Now, if you don't have that, you can go over here into extensions and look for React something components.

**1:55:26** · Yeah, it's uh going to be this one, I think. React snippets. There's other ones with very similar snippets as well. And I'm just going to double click here. Ctrl + D to select the next instance and just get rid of that. Now, I think typically what AI likes to do is do export default like this rather than coming after something like this. It doesn't really matter. I just I just got so used to this that I do it this way. Now, we actually need to install our dependencies. So, I'm going to hit control/commandbacktick to open the quickly open the terminal.

**1:55:57** · You can also come up to view and open the terminal that way. Now if I do Ctrl P and just search for package.json hit enter to go there. You can see that we have a lot of dependencies that V uses and React app uses. And now we need to put our 3JS stuff in here into and it'll show up into our node modules folder when we download it. So let's type mpm I like so. So we have React 3 fiber, React 3 Dre, and Gap. We're going to install a little bit more later, but for now that's enough for us to get started.

**1:56:27** · Okay. So in our 3D experience, if you go to the React 3 fiber documentation, what we need is a canvas as mentioned earlier. And inside the canvas, you can add some stuff like a mesh and a box geometry and like some materials and stuff like that. And then it's just showing the equivalent of what you would have to do in 3GS instead. What you can just do in React Fiber. If you don't know regular 3GS, it doesn't even matter when you're vibe coding. Just know that this is not as scary as it looks. Again, if I go into Blender, like this entire viewport is like the canvas.

**1:56:56** · So, if I let's say if I get rid of the canvas, I just got rid of the canvas. You can see I can no longer see my 3D scene. So, that's why we need a canvas. Something like this. So, if I go back to the Lando Nor site, I just searched for three here. You can see the canvas element over here. I delete that. It no longer exists. And so, so forth. Undo that. You can see it's back. Same exact thing here. So, of course, I did not want to type that out myself. So, I just copy and pasted and add that stuff there. So, we can just copy and paste that. And just like so. Now, they did give us a bunch of filler stuff.

**1:57:28** · So, let's also just make sure to get rid of all that as well. We don't need that. And we can control X to quickly get rid of some of this stuff. And now, we should just be able to type experience. And you can see it finds that there. And we can just hit enter to confirm that. And Whoops. And let's just close that out just like so.

**1:57:46** · Now, if for some reason it's not showing the import, you can just hit control spacebar or command spacebar and it will automatically detect where it's from and then you can just enter enter it that way. All right, let's clean up some of the other stuff that we'll never need.

**1:58:01** · So, I'm just going to go over here and I don't think we need anything here. So, I'm going to controll X and get rid of everything here. Same thing here. I don't think we have to I don't think we need anything here. Actually, let's just get rid of all this stuff. We might need some stuff over here later. Uh just for just for formatting stuff, I don't know.

**1:58:21** · The global selector to select everything. So that includes literally everything. And we'll do body and HTML just to really ham it down. And then P0 for no padding on anything. M0 for no padding on anything. And we want border box sizing. And we want border box just like so. Let's run our development server just to see. And hopefully mpm rundev that is right over here. by the way, for the live coders. And I'm going to hit control or commandclick just to open that.

**1:58:48** · By the way, if you want console dev tools, you can rightclick and go into inspect, and it'll show up here. And then you can search for three or canvas since we only have one canvas.

**1:59:00** · You can search for canvas as well. And here you can see it. I just use the hotkey with this control shift I or Windows here. And on Chrome and of course it is a little bit too small. So let's select the root over here. You can see the canvas by default will take I think internally is 100% by 100%. And the root the root right now is limiting constraining it to 150. You can see it's an ID. So we have to use hashtag hashtag. Let's come back to over here.

**1:59:26** · And I think I'm just going to shift alt down arrow here and then shift enter to enter a quick space up there. I'm going to do hashtagroot and yeah I'm just going to do height 100% and let's do width 100%. Since this is already here, we can actually just get rid of this and just leave it for the global selector over there. Not the best CSS, but it doesn't really matter. And then we don't want any overflow bars if there's anything. So, we'll just hidden cuz everything will be just full screen. And if I go back now, you can see the canvas spans to full screen. Amazing. So, now we actually need to load our Joy file.

### Preparing GLB files for the web using custom Node.js script, AI, and gltfjsx

**2:00:00** · And then we want to put it in an easy way where we can just modify it pretty simply. The easiest way to do that is using this online tool over here. And if I click and drag up my GB file, you can see it's going to convert it to JSX or React code that we can just use. So basically, it's just loading our GV file and then converting it into that kind of just looks like Blender at that point.

**2:00:20** · We have our position rotation. I click on here, hit N. We have our position rotation. Well, they call location here, but you know, same same stuff, right?

**2:00:28** · Except this is just like text instead of like a user interface with text. Now, again, we have five of these. We don't want to do every single one. And then since we all have our KTX textures separate like for each one of these like let's say we want to do winter let's see winter one over here we have to attach replace it over here and then winter two we have to replace it over here winter three we have to replace it and then all winter threes have to be replaced yada yada yada blah blah blah now that's not terrible but of course we can use AI to

**2:00:59** · generate a script for us to speed up this process as well if you come over to the top here you can see that it's actually based on another tool which I used in my previous videos. This is a command line tool I was talking about earlier. So you basically convert your model GB file with the -asht and that'll apply the Draco or Draco compression that Blender did. So that's why I said it didn't really matter if you turn it on or off. You can see there's some other options here like texture resizing. We already did that so we don't have to worry about that at all.

**2:01:30** · And this also requires your texture to be embedded in the model for that to work. Now, since we want to keep things separate, even if they have different materials, we don't want to join compatible meshes and pallet materials either. So, we're going to do dash j and dash m. So, you can imagine mpxg tof jsx model.gb- t or d-t transform or dash capital T, whatever. Same thing. But again, we don't want to do that five times and then copy and paste five times because that's a lot of work. So we can automate it with AI to generate us a script.

**2:02:00** · So for the script, I'm actually not using PowerShell, even though you can totally use a PowerShell script as well or bash script if you're on Mac, but I'm going to be using Node.js instead to run a JavaScript script. So I'll talk about this in a little bit, but let's just copy it for now. And I'll put it on that documentation as well if you want to use it. And I'm going to go back to my code here and I'm just going to create maybe like uh another folder here called scripts. And this is just for us. So, it's kind of wherever you want to put it.

**2:02:30** · And I'm going to come over here, process models, and I'll do js over here, and just paste that in there.

**2:02:36** · Basically, what I did it to do is find an input directory where all our original models are, and then export it, export all the transforms into our public/models folder, which we need to create. And then all the JSX over here, we want to put it into another folder here called components. Well, I'm actually going to change that to /experience/models.

**2:02:57** · I did not update that yet. And then we just replace a lot of other stuff. So for example, as I said, we used the naming convention of here to determine which texture is going to be loaded and assigned to which single one here. So we don't have to do it every single time.

**2:03:12** · That might not make a little bit of sense. Let's just see it in action first and then I'll talk about it. So let's go in over here. Let's create our models.

**2:03:20** · And since we're here, we might as well create one for like images. I don't know if I will cover images here or not, but whatever. And then textures like so. And then in source over here, let's create one in experience here. And oh, sorry. I I already copied and created models there. So, we can just come over here now. And we should just be able to type experience and then slashmodels like so.

**2:03:43** · So, that should be it should show up into this file over here. All right. So, I haven't tried it yet, but let's just see how good it gets. I have a different one that I typically use, but I just want to show you that you can totally use AI to do this as well. So, let's just come over here and copy this over here. Let's go into package.json and add to our scripts over here. And our input for our models needs to be in dot /rawassets. So, let's also come over here into source and just create raw assets as well. Raw assets and sorry, scripts should be into root level.

**2:04:14** · So, let me move that. And then of course we also need raw assets, the folder that has all your stuff. So let's come over out into the root directory and do raw assets as well. So basically it's like node run script/process models.js which is in here. And since this is running from the root directory, it's just going to go into the raw assets. And these parameters are actually optional. So we don't need them. But just to show you, we can also just change the path over here. So let's go to our GB files.

**2:04:43** · Let's just shift select all of them and drop them into raw assets over here. And let's control C to cancel the development server. And let's do mpm run gen models just like so. Also, just FYI, I might give you a different script in in the the coding followalong files than the one that you see in the video.

**2:05:06** · It doesn't really matter. I just wanted to show you that you can automate it. I use a different script that does a little bit few more steps, but I just wanted to show you that you could totally use AI to generate you a few scripts. So now when I run mpm run gen models, you can see that it's going to well they nicely added some logs for us to see what it's doing. Here you can see models, it took our raw assets, put it in our public models folder. Great. If we rightclick here and reveal and file explorer, you can see that. Okay, cool.

**2:05:34** · And now they're smaller because there's a little bit of compression. If you're using complete flat planes, you might actually not want to compress them, but it doesn't really matter for us. It's nonsignificant. And if I come over here, let's see. It's not exporting here, which is probably something I need to fix in this script. You can spend some time reprompting it if you want. But now, if I take a look over here, you can see that for every single one, let me just save this for example.

**2:06:00** · It basically you can see that it took the name index and then loaded that texture for each single one that we had in our textures folder here and then replace the material with that texture. So here underscore 2 is using texture 2 underscore one over here is underscore one and then so on so forth underscore3 is now using texture 3 and so on and so forth. So that saves us a lot of stuff.

**2:06:25** · This one also imports from use k2x2 texture which is a utility function that I will talk about in a little bit but for now you can just think of this as a way to load that image texture. The other thing that this adds here is the /models over here. That way we don't have to replace every single one with the path of slashmodels. And then also by default there's no default here. So the script also adds the default then there as well.

**2:06:50** · So you can see that I might give you a more correct script, but I just wanted to show you that in like three or four prompts, you can do a pretty decent thing that will save you about an hour worth of work or 30 minutes at least. So now I just want to show you that every time you start a boiler plate, this can be part of your script and you just run the script and then you get all your JSX files straight out of the bat. This script again is a little bit buggy. I'll give you a better one after it's polished.

**2:07:16** · But now we can just click and drag these and plug them into models over here. And I'm just going to move that. And then we can just delete this folder over here. Just like so. The script does not handle the moving characters one, which is okay because there's only one texture. So we can just control X to get rid of that. And then we named it moving characters, not moving characters\_1. So we can just get rid of that as well. But everything else is fine over here. So, let's just go back to our textures. Oh, never mind.

**2:07:46** · I did name it underscore one. Just uh I guess we should probably name it one without the actual name there.

**2:07:58** · So, my bad. And now we can just come over here and it's already pathed to textures. So, we can just drag it put it in there just like so. All right. So, now let's talk about this loader over here. Now, I just realized it should not go back two directories. It's going out of models, so it should only be one. So, I guess I need to fix that script. Yeah, don't worry about it. It's like really bad. I will I will get you a better one.

### Notes on loading models and analyzing script faults

**2:08:25** · And we should just be able to come over here and just replace it like here and replace all just replace all them. So, let's just come over here and let's do KTX loader. GSX just like so. Now, typically when you're working with KTX textures and React 3 fiber, you can use this one from the React 3 J or dry ones over here. At this time of recording this video, it does not work with the web GPU renderer. It has not been updated yet.

**2:08:54** · It probably will be in the near future, maybe in like the next month or two. So, you can give this a try rather than creating the custom one that I have. So, I'm just going to copy it and paste it in over here. created is actually based on the one that is default in react vary fiber. So if I come over here and go to the source code over here and you can see that it's very very similar to what they did over here.

**2:09:19** · So the issue basically is something in over here I think it's might be the 3 standard library that's not updated yet.

**2:09:25** · The K2X2 loader for the regular 3GS does work with web GPU. So here you can see that it does actually support it. So, it's just this hasn't been updated yet at the time of the recording, but it probably will be pretty soon. I just created a loader instead based on the source code of React Fiber itself. Now, there's a few other things that I added that I want to talk about. So, just ignore all the nerdy internal stuff for now.

**2:09:51** · I this kind of technical stuff you don't really actually have to know cuz that's going to be handled and abstracted with React 3 fiber. But, one thing I do want to mention is this over here. So, we have the texture URL. So if I go back here, it's just literally where the image texture is. And then we have it if it's transparent or not. Like does it have an alpha channel? Most of us don't. In my panda one, I had all of them. So we can actually set a default here of false for us. And then anything that needs transparency, we can set true. So if you want that's like over here, right? We can just like do false.

**2:10:23** · The ones that need alpha, we can do true. And then that's what this is here for for alpha test value. I don't think it's going to matter too much what what we set this as, but basically it's the threshold of its opacity value to whether discard that pixel or not. And then side is kind of exactly what you expect. I just defaulted as front because we fixed all the normals before we export. If there's for some reason you need to look at like the back side of your meshes and you can do like three dot double side.

**2:10:48** · Of course, that means way that you baked though when you look behind it, it's going to show you the other side of the color that was baked in the back as well. that might be fine because we have uniform lighting, but just to keep that in mind. For performance reasons, we're just keeping everything in the front and we're not going to be looking at anything in the back. But if we need to, we can also manually set that as well. Same thing with transparent. We're setting default false. Saves a little bit on performance. Probably irrelevant for us, but hey, we only need to use the things that we actually need to use. Anyway, we'll take a look at this later.

**2:11:20** · Wherever the text is, but for now, let's just switch over to the WebGPU renderer.

### (Optional) Switching to WebGPU renderer, I never end up using it lol

**2:11:25** · By the way, TSL is completely optional.

**2:11:27** · If you want to follow the rest of video in WebGL, you can totally do that as well. I'll definitely make sure to mark the positions when you do need to switch to WebGPU if you want to. So, here it is in the documentation over here. And sorry, I forgot to copy and paste this.

**2:11:44** · I don't think we're going to have use frame in here either. Again, if it doesn't really matter if you don't know what's happening over here. So basically, instead of using the WebGL renderer, we're setting the prop of the GL canvas to the new WebGPU renderer.

**2:11:56** · Everything we're using for the WebGL renderer, pass it into the WebGPU renderer instead, and then initialize it. Wait for that to be initialized, and then return it, and then we can use it.

**2:12:07** · Extending here is just so it can work within JSX. It's actually completely optional as well. You can also just do something like this, like this. And instead over here you can just do web GPU let's see web GPU renderer like so and just uh you know deconstruct it like this and this would be fine as well. It doesn't really matter too much but yeah again this is optional and I don't even know if I'm going to cover it in this video.

**2:12:38** · And let's just undo that because let's read the three here because that's what we were extending there. All right.

**2:12:46** · So now we can go into our scene.jsx like so. And we should just be able to good to go and import. This is something that your upgraded script can also generate after it generates to JSX. It can generate scene.jsx to import everything.

**2:13:02** · So we're kind of wasting time here, but it doesn't really matter. Moving characters. And I don't think it's going to find an import because we didn't name the default import, which is fine because we can choose the name right now. And I'm calling it moving characters. So, I'm just going to do moving characters like so. And we're just going to import that from dot /models over here, and it'll just find that for us. Now, we can do npm rundev just to make sure we still see it. And of course, there's an error. And yeah, we need to change it to K2X2. So, f my script, I think. Yeah, all these.

**2:13:35** · Oh, okay. Sorry, that's my bad. Let's just uh let's just search for this in all our files. Control shift F. Let's search for this.

**2:13:47** · Let's make sure I'm not replacing anything by accident. Cool. So, let's just come over here. Replace. And we're just going to replace this with two.

**2:13:54** · Like so. All right. Let's just replace all them with K2X2. Hopefully, no errors. Now, we're still getting an error here. And I think that is because I did not upload the basis into our public folder over here. And in the K2X loader, you can see the basis path is to basis, but it's not there. You can also just point to the one directly known modules, but we're just going to put it in our public folder. So, let's come over here and then in three, we're going to open up into examples JSM and let's take a look for libs.

**2:14:26** · And we're just going to copy control C this entire folder and paste it into our public folder over here. Let's just save and everything. Control shift R for hard refresh. And voila. Take a look at there. We have our objects here. Now, the color is a little bit off because by default, there is some tone mapping on it. So, let's go back over here and let me just turn that off. And let's go to experience.js. Whoops, I accidentally activated my Chinese. And we can come over here and do flat equals true. This will get rid of the tone mapping. Sorry, it should be flat.

**2:14:57** · And now you can see that it looks like the way that it looks like in Blender. And we can take a look.

### Switching to flat on Canvas and analyzing loaded models

**2:15:03** · And wow, it actually looks pretty good.

**2:15:05** · Now, if at any point it looks too blurry or it's too messed up, you can go back through all our steps and again, you can just compress from the 4K one instead of the 2K one. See how much that destroyed it. The the colors are from the the compression method we did. And then the blurriness is definitely rescaling it from 2K, but from far away, it's actually not too bad. I might go back to the 4K ones and stick with that because it's a little kind of blurry, but doesn't really matter.

**2:15:36** · But yeah, it's really really up to you at at this point and just use your determination for that. Go back to scene.jsx and just shift all down arrow to finish importing the rest of them. I'm not going to use underscore one or like winter or whatever. Actually, yeah, I'll just call it like winter. So, just like so, we imported everything. And going back here, you can see I am a complete idiot because I did not actually put this into conversion. You can see that I have it over here. I did not put it into paper textures to be converted, which my bad.

**2:16:10** · Now it's in paper textures. And I don't actually want to redo everything. Uh so I'm just going to do already converted, but it it honestly doesn't really matter. Um but yeah, now I'm just going to select everything. we already converted. Uh, and just move it into already converted just so we don't have to do everything ever again. And let's just run with this one with PowerShell again. So, it's going to put it into our 2K PGs. Hopefully, yep, there it is at 2K now. Again, if you want to do it from the 4K, you can totally do the 4K.

**2:16:43** · Just make sure to change the PowerShell to just convert to like so. Sweet. It's done. And there it is. So, now we can just click and drag this and everything should be good to go. Of course, there is one more error, and that's because scene 4 does not have a fourth texture.

**2:17:00** · So, again, I need to fix the script. I definitely need to fix that script for later. And it does seem like it's looking good. Now, it's a little too far stretched for like fisheye sort of effect. So, let me go quickly back to experience.jsx and let's come over here. Let's change the camera FOV. So, let's come over here, camera, and let's change the field of view to something a little bit more natural. Maybe like 50 over here. And let's refresh the page and see what we get. Yeah. Okay, that feels a lot better. It's slush fish eyes lens.

**2:17:30** · So, now's the time to just look around your scene and look for any issues. Now, there probably going to be some. There's always some sort of small issue. Like here you can see that over here my images are very blurry and that's likely because of the compression method as well as the downscaling to 2040.

**2:17:51** · I guess I would have known that in advanced already from experience, but I just wanted to show a way to automate everything. But this is definitely something I would probably consider keeping 4K and trying a different compression method. So you can try 4K and then compressing after. And if that still sucks, then try the other K2X method. And if that still sucks, maybe try like WEBP or something. And I know it's the compression method or the downscaling because here you can see that it's perfectly fine even if I use the PNG version, which I can show you if I go into already converted ones and go to the image ones.

**2:18:23** · You can see that it actually looks fine as well. So it's definitely a compression issue or a downscaling issue or both. There's some Z fighting on some areas over here. You can see that this see that this leaf is on the floor and it's Z fighting there.

**2:18:40** · Then some baked things I didn't really do properly either. Like this leaf over here was overlapping. So when it baked it turned black because it was Z fighting. Now this is a very easy solution. You can just adjust the UV map and reexport the GB and you don't actually have to do anything. You can just replace the GB with the new UV map there. So those kind of errors you can fix there. But yeah, you're probably going to have a few errors and some of them you might want to keep high resolution. So, really depends on your scene. Anyway, since we have something, let's just deploy this and get a little celebration.

### Pushing to GitHub and Deploying with Vercel

**2:19:11** · Create a new repository on GitHub. I already have one, so I'm just going to use this one. Copy this command. Control back tick or command back tick. Just do that. Control C to cancel it. Get init. Let's add the origin. This GitHub repo. Let's add the origin here. And let's just add that.

**2:19:27** · Let's get add everything. get commit and we'll just like woo first commit. Let's go, dudes.

**2:19:36** · And then we can just do get push just like so. And whoops, we need to set the upstream origin main there. And after this, now we can just do get push. We don't have to set upstream anymore after. Well, let's just refresh our page. Amazing. And it's all there. All right, let's go into Versel. Create account if you don't have that yet. And then you can just come over here, add new project. And since you just pushed to it, it should be at the top. It should automatically detect it after you connect to GitHub. And you just import it. And here you can see the build. It's going to run that build.

**2:20:06** · And we don't have any special environment variables, anything. So we can just hit deploy. And now we can just go here and celebrate the fruits of our labor and share this with our friends. Now we need to make some of those corrections. I'm going to do those off camera because I don't want to bore you. Unless there's something special, then I'll of course put it in the video.

**2:20:23** · So because I had to make some adjustments to the unwraps, not the baking unwraps, uh the original UV maps, and I didn't want to touch that by accident for any case, I generated another script that would just select everything in a collections subolctions to select back to the UV map. All right, so the whole entire goal now is just to make adjustments to things that are either overlapping or like you kind of want to change the texture up. But let's say this beach ball over here is too low on the amount of texture.

### Making Blender adjusments and more tips with JSX, models, and workflow

**2:20:54** · Well, I can just select it and with the original UV map, right? We can just like do something like smart UV unwrap. And then we can just adjust how much texture we want to show there on the beach ball.

**2:21:08** · And now we just reake with that. And we don't have to do anything other than just convert that texture again and replace it. So you can adjust the lighting, you can adjust uh you can adjust the positioning and everything.

**2:21:20** · Like if you want to bake this beach ball somewhere else, you can totally do that and it will not affect what your process is in the end because the UV map doesn't change. You technically only have to re-ake the ones that you think are having issues mostly. But if you change the entire scene lighting, then like this global light over here, then you're probably going to have to well, you will have to bake everything. Otherwise, it'll look a little bit off in in some scenes. Well, I guess depends on your style, but most likely you have to.

**2:21:48** · So, basically, the idea is you have that other Blender file for the new baking adjustments. Again, you can change like color, yada yada yada, size, texture, positioning, so much so forth. and your original one where you adjusted everything and moved like all the characters back. You can see this is my original file with that. As long as you don't touch the symbol bake, it's fine to move anything anywhere you want. Like let's say you want to move this arm over here for some reason.

**2:22:17** · As long as you don't adjust this over here, whatever you bake on your new texture, it'll just automatically apply there because the UV map doesn't change. So you have your original file where you moved everything and probably replaces to reexport as GB.

**2:22:31** · if you need it. And then you have the other one where your bakes your mesh bakes don't matter. You can just like hide it every single time cuz you're never going to touch that. It's just to generate some textures. Now, if it's an object that is joined together, you don't have to touch anything in code.

**2:22:46** · Like if you move this object over here, you don't have to touch anything in code. You can just re-upload your GB and replace the old one and it'll just work out of the box. Now, if it's a sing single object like this and you move the position, well, you can imagine that is going to change this position value over here and then your JSX will no longer match the information and data of your position in your code. Now, the great news is you don't actually have to go through that entire process again.

**2:23:10** · So, here's another 3JS YouTuber, Wawa Sensei, who has a really clever solution. glTFJSX will generate stagnant or hard-coded positions every single time, but all you have to do is just get your position instead of the hardcoded position. Now, this is something that I need to add to the script. So, it does it automatically cuz right now it's pretty tedious where we have to change each one of these in code to basically let me see it's just going to be nodes and then it should just be yeah position instead. So, it should be like this.

**2:23:41** · I would have to do that for every single one. If you're using like cursor or some AI, that would be really easy just to prompt and have it replace that with the name of the node plus its position for every single one. I'm not using an AI code editor, but if I was, I would just prompt it there. But since we're going for a free version, you can also just prompt that directly in a script and let the script change that later for you. If I have some time, I'll update that in process model script as well.

**2:24:08** · I'll also mention like sometimes you'll get like something like this where it doesn't really look like Z fighting, but it kind of does. And that's typically just because of like how accurate the algorithm is when it determines the depth in large scenes. So, I think I did it in a previous video, but you can actually just activate. So, we can actually come here and spread the props and let's just choose our logarithmic buff depth buffer and set that to true.

**2:24:38** · Again, you don't really have to know what this does other than by default it's on linear and logarithmic is just a little bit more accurate. Of course, at the cost of performance, but it doesn't really matter. And we said true. Okay.

**2:24:48** · Some other niche issues you might run into when you see like these black things over here and it's not on the texture and it's not Zfighting, that actually means Draco compression messed up with your model. And given that we have a lot of low poly models, it's not a surprise that it's happening and everything's like flat. I think I had a lot of vertices here and it's like merging them together. That's kind of a destructive process of what Draco does.

**2:25:10** · So, all I did was reexport the model and replaced the compressed one with the non-compressed one. You don't have to change anything in code because it would automatically detect that it's not compressed and loaded anyway. Yes, the file size is a little bit larger, but no one wants to look at these black lines over here. For process models, that just means getting rid of the -ash t. So, you can probably put that in as a prompt if you want to. So you can get rid of this if you're working with like low poly stuff. You can get rid of that and that way it won't transform anything. And then I think these are associated with dash t.

**2:25:40** · So if you don't have dash t, you don't actually need to explicitly keep those away either. So that would just be one way just to do it without compression. And just looking at this, there's another obscure bug I want to point out. You can see as we get far away, we kind of get like white edges and as well as like some black over the white line and text and stuff like that.

**2:26:01** · And that's likely due to mint mapping, which is basically the idea that as you get farther away, it's going to use your lower generated textures like 512 x 512 to save on performance. But I've also heard something like mag filter and min filter in 3GS and there's like different algorithms for them that might produce different results. For something like this, I probably just want to disable mapping entirely. So what we can do is come into texture over here. Again, here you can play with like texture.mmin filter or whatnot. This is just a loader, the KTX loader.

**2:26:32** · I might give you a different one and and rename it later.

**2:26:38** · It doesn't really matter, but the whole idea is you can just do texture.generate maps. And we can set that to false. And this time, it will always show our 4K textures no matter what. Now, of course, there's some downsides to that besides adjust performance. You can see like it's a lot crispier. Now that I go back here, the text is no longer black. And I can just show you that right here. And it looks so much cleaner. And the images themselves also look a lot cleaner. And again, we're on 2480 by 2480. So that virtually had no difference from the 4K, which looks really nice.

**2:27:10** · Now, you might be wondering, is that why in Blender it looks perfectly fine, but in 3GS it was like really blurry.

**2:27:19** · And the answer is yes. It's because of mapping, but it's also because the UV was really stretched. and blenders.

**2:27:25** · Blender has a lot more forgiving algorithm there to make it look nicer than than 3GS which you have to set which as you can see we just set and it now looks like Blender. So now we're always seeing our 2K textures no matter what. And you can just see the quality difference. It just feels so much nicer here. Of course at the cost of performance, but from my experience it's probably not going to be too much of an issue for these kinds of scenes. Now there's other drawbacks besides performance. You can see some shimmering when we get further away like these textures over here.

**2:27:54** · Now, I actually really really like that shimmering effect for this scene, but yeah, it it it's really a case by case basis. For us, it's probably not going to be an issue, but use your best judgment. The last thing I want to mention is you might see some gaps over here, and that's just because the scene background is black. Sorry, I mean white. So, we can just change that to fill it up. I think later I'm going to come and just make these edges a little more unnatural. Oh, sorry, natural, but like uneven. That way it looks a little more natural. But for now, we can just like attach a background color.

**2:28:25** · So, we can just do color of like something like black. So, we can just uh and whoops, I need to do arcs. And now you can see that it fills up with the black and it's not as noticeable. Great. And of course, face orientation as well. You can see over here I can't see there. And then on this side, I can see there. I could go back into Blender and flip them, but I actually want both of them on both sides. So those are the one of the ones that I would pass in double face side.

**2:28:52** · Now if I come back here, we could set each one of these to undefined if we wanted to. And then the last one, flip Y to true. But typically when you have a lot of optional things like this, you deconstruct it into an object. So I can do options over here, set it equal to an empty object, and I'll do const over here. We deconstruct it from the options object that we pass in like so. And now, and now essentially we're just using key value pairs to select what we want. So we can come over here, come over here and use flip Y.

**2:29:24** · And we'll just set that to true. Just like so. Sorry, not flip Y. What am I talking about? It should be side.

**2:29:32** · And I should it should be double. I think double is the one that I'm going to use. And I'm going to set it to double. You might see a different loader. Oh, I only have front side or double. So it'll just be double then. So it doesn't matter what I name it. And let's just see. And yeah, now you can see I can see it on both sides, which is exactly what I want there. Also, you'll notice that I am using WEBP here. I'm going to switch back to K2X. I was just testing how it look in WEBP. When you're using something other than K2X, you typically have to set flip Y equals to false. Otherwise, it will look like completely jumbled mesh.

**2:30:02** · So, if I just show you that real quick, you can see everything looks a little bit chaotic here. So, when you're using K2X, you don't have to do that. But when you're using something else, uh just make sure to do that as well. Of course, if you also have it embedded as part of your model with WEBP, you don't have to flip it either because it'll just work out of the box that way as well. Yeah, I'm going to go back to K2X. Again, it doesn't really matter. Just try and error things until you get something that you like. All right, so at this point, I think we're pretty much ready to go. We can start moving our camera along a curve.

**2:30:33** · Right now, our camera is free roam, and we want it to travel a certain path and look at certain destinations along as we scroll. So, we can actually configure that path in Blender rather than doing it manually.

### Moving camera along curve, preparing curves in Blender

**2:30:47** · In my previous video, I did it manually.

**2:30:49** · And this time, we're going to configure that in Blender first. Okay. So, it doesn't really matter which file you want to use, whether it's your one for textures or the ones that you move stuff out of the way. Anyway, I'm just going to save incremental as usual, just in case I if I ever mess anything up. All right. So, the first thing I want to do is create a curve. I'm just going to shift right click here. We could build it from the scene if we wanted to, but I don't know if I want to do that. I'm just going to create a circle. And it's at 32. It doesn't really matter. We can always change that later. Let's just go into wireframe. And this will be our moving.

**2:31:20** · Well, actually, let's do the camera one first. So, again, it doesn't really matter. And that's a little too many. 32. So, we can come up to select, check or deselect, control X just to dissolve some. And now we have 16.

**2:31:33** · Again, it probably doesn't matter. Now, when we're creating the curve for the camera, we kind of want it to be even in points because when it comes to moving cameras along curves, more methods, like more manual methods, they work a lot better when your points are evenly distributed. There's a lot of methods where your spacing between your points don't affect it at all cuz you like pre-animate it or whatnot and so on so forth. But there's a lot of methods that are very easy to implement and they rely on, you know, the distance between your points to calculate things.

**2:32:00** · So I try to keep them even but again it doesn't really matter if you don't can't keep them even. Now I don't like seeing this sort of visual because it doesn't really show you the kind of curve that I want to use in 3GS which is a catal ROM curve. So we can actually fix that. We can come back into object F3 and convert it to a curve just like so. And now when we go into edit mode we can come over to curve and we can come over to set spline type and then we can change it to a nerves curve. And now you can see that it's very it looks a lot more bendy and like a circle just like so.

**2:32:33** · Just like so. Right. That is completely optional in terms of Blender because we're just exporting the control points and using a curve in 3GS, not this actual curve.

**2:32:43** · This is just for us to use in Blender.

**2:32:47** · So, we can just do that. And this will be the path for a camera. And of course, you can adjust it and so on so forth.

**2:32:53** · Now, we need one for the moving objects.

**2:32:55** · So, we can just actually just duplicate this. Unless you want to for some reason use a different sort of curve. You can also rightclick and do things like subdivide. So add like another anchor point and whatnot. I don't think I need to do that. So I'm just going to rescale this one. And it's just going to try and fit the moving character path over there. So that's what I'm going to do.

**2:33:15** · Just scale that up. We'll make some adjustments to these later. It doesn't really matter. And let's do now the other thing we want to do is make one last one for the camera look at like where the camera is going to look at.

**2:33:28** · And one of the easiest ways to do that is make make a dummy object move along an invisible curve and have the camera look at that curve instead. If it doesn't make sense yet, I'll show you what that looks like in a little bit. So don't worry if it doesn't make sense.

**2:33:40** · And then this one is going to be the camera look at curve. So sorry, I should be renaming these. So, I'm going to do F2 and I'll do this camera look at curve. Naming convention doesn't really matter here cuz we're not going to be using these curves outside of Blender other than just to export the data. This one I can hit F2 and I'll do that camera path curve.

**2:34:01** · And then the one in here, I can do that F3 uh sorry, F2 moving characters like Okay, so now we should be able to add a camera. So, let's add a camera. If you don't have a camera, you can add one. If you do have a camera, just use that one. Not a big deal, unless you want two cameras for some reason. Here, we can change this to the 3D viewport.

**2:34:24** · Just over here, let's enter camera mode with numpad zero, and let's change that to 1920 x 1080.

**2:34:31** · Doesn't really matter, but it's kind of like up to you. If you want to do a mobile version later, you can like flip those. Uh, so this will be our camera version over here, which is super cool.

**2:34:41** · And then we can just get rid of the shader editor because we're not going to be using that either. And if you don't have a numpad, you can also come into view and come to cameras and do active camera. And that'll do the same thing.

**2:34:52** · Sorry, it's because it so it got rid of it. But now you can just go and you'll see it becomes view. All right. So now when we move that we have the what the camera is actually looking at. And now if we want to make this follow the curve or follow the path, well we can come over into object constraints. So, it's one of these. Yes. So, it's right there.

**2:35:12** · We can add in relationship a follow path and just select our curve object over here. You might have to apply your scale. So, I'm going to apply my scale just to make sure there's nothing buggy.

**2:35:21** · You might have to play around with some of these axes, but it seems like this is working for me. So, I don't really have to do anything. So, now if I check and go into top view, I should just be able to Yeah, it just offenses really cool.

**2:35:32** · All right. So, we need to do the same exact thing but with like a dummy object. So typically when we work with dummy objects, we just do empty. So we can do like empty plane axes. But if you don't want to do that, it's fine. You can just use like a cube, right? So we can just add a cube. And we're going to do the same thing. We're just going to do a follow path. And then this time we will just select the camera look at curve this time. And it's off into oblivion. So let's just make sure we're in camera.

**2:36:00** · Let's just select all the curves actually and apply our scale. to apply our scale just to make sure all this work. Whoops. I didn't actually apply scale for there. And now I apply my scale. And now it's there.

**2:36:11** · Super cool. But once I animate this, it should probably follow the curve as well. Let me just make sure that is accurate. Yeah, indeed it does. Cool.

**2:36:18** · And let's just make that a little smaller. Our scale. Cool. And now let's go back into our camera. Where is it?

**2:36:25** · I'll just select it over here. And now we want to give this one more constraint. And it will be the track two constraint. And basically we'll just set it to the cube. So I'm just going to select the cube over there. And now you can see that. Let me adjust the cube. So let me select the cube. As I adjust the cube, it's going to keep looking at there. And when I do with the camera and adjust the camera, you can see the camera is going to move along its curve while always looking at. So I'm looking over here at the curve over there.

**2:36:51** · Now, it's kind of tedious that for one of our areas over here, actually, let's set both of them to zero real quick. So, I'm going to set the cube to zero as well.

**2:37:04** · Cool. And luckily for us, it's actually pretty similar in where it's at. But let me actually just move this cube so it's like right there, you know? Just really wherever you want to start. Uh, just do that pretty much, I guess. And then you can always adjust the curve. So, I'm just basically trying to get a good position. I'm going to do GZ. And I think look at I want to look at the starting area over there.

**2:37:31** · So I'm actually just going to I'm just going to make some adjustments to my curve off screen or on screen to look at the path that I want to and and so on so forth.

**2:37:43** · So I'm actually going to move the camera to as well. Again, it's going to follow the curve. So we it doesn't really matter where it's going to go. It's going to follow that same circular pattern. Again, make adjustments to your curve however you want.

**2:37:59** · It doesn't have to be a complete circle.

**2:38:01** · Now, one painful thing I will mention is doing the offset for each single one is definitely kind of a pain in the neck, right? Like, is there some way to automate it? And the answer is yes. So, it's called a driver. And if you select this and right click over here and add a driver, you can type a formula here. And the formula to do it over time is frame.

**2:38:25** · And then if you want to determine how fast it goes, you can like divide it, right? So frame 10. So I must have accidentally hit spacebar. Uh but we'll see. And here you can see now it's just animating all across our path. Super cool. So if you want to, you can see if I go to the where is the timeline? Yeah, it's right here. You can see that I'm going around in circles and so on so forth. That and of course we can do the same thing for the cube as well. So, let's do the cube. Click add a driver and let's do frame divided by 10 like so. And it doesn't seem to be playing.

**2:38:58** · Maybe we can click animate path. And now we hit play. And okay, now it's now it's updating. And if you just don't even want to bother, you can calculate for a perfect loop, but I it doesn't really matter. I'm just going to turn this into something really big for Oblivion. And uh yeah, now you can see that it's just working. And of course, you can use other things like sign if you want to use sign multiply and offset. I don't know, maybe like 10 or something. Now, you can see it's like offset. So, yeah, really up to you if you want to use drivers.

**2:39:27** · And now what you can do is just hit space bar to play it, space bar to stop. And whenever you're at a different location, like you can just scrub along the timeline over here, and then make some adjustments to your curve. Now, we want to make adjustments to the curve and not the object because it'll just be easier to manage that that way and it kind of cuts out a few of the steps. So, I'm actually going to position this right at the center of this curve.

**2:39:49** · If you want to, you can like shift S cursor to selected and then select your object over here and do selection to cursor just like so. So, we know that it's in the center there. Can you do it where you base it off the object? Yes, absolutely. You can base off this constraint here for like a full of loops. I don't know where it loops where it goes and starts at the center.

**2:40:14** · And you can either use that animation key frames directly as and just copy that look at value in code or you can use different positions along those key frames as your new curve points. Both of those take more time than just adjusting for the curve itself. So, I'm just going to make sure that it's adjusted partially. So, I'm just going to make sure that it's just based on the curve and make adjustments to the curve and not the object.

**2:40:40** · And if you want to keep it a little bit more consistent on the curve instead of offset, you can do follow curve and that just makes it a little more cleaner that way. I actually want to give out another community shout out. So, Sentry just made this. I think this is from the Blender docs or some sort of Blender guide. I could probably search for the image on where that is. I will put that in the description below.

**2:41:04** · But you don't actually have to align it.

**2:41:06** · You just have to align it to the origin of over here. So if I turn this off, you can see if I do alt G and alt R to ro reset everything like the rotation and the position, it'll perfectly snap over there. So you can see that one more time. Let me do that. But over here, I'll do alt g to reset its location and alt r. But it doesn't really matter. Alt R because it's still doing this. It's still tracking. So, Alt R doesn't really mean anything. Same thing here. We can do Alt G and it'll snap to perfectly align with the curve. Now, cool.

**2:41:36** · And that just makes it a little bit more accurate. Thank you, Sentry from Discord. And if you're not on Discord, definitely make sure to join up. Last thing I'll mention is to set your camera focal length. So, you can come over here and set its focal length. And you can convert that to an FOV value in 3GS later. So, it doesn't really matter what you want to choose. I think I'm going to stay with something a little bit more neutral. If you want like making things feel super large, you typically turn this down really low.

**2:42:04** · And if you want to make something feel really really flat or like zoomed in, you can turn it up a little bit. These are pretty neutral one. So use whatever you want. Now I will say don't be afraid to rotate it.

**2:42:18** · If you need to rotate the starting position. So I think right now like the starting position of the curve is not ideal. So we can actually select both the the curve over here and rotate it and I want it to center on over here on the winter scene over here like so. If it helps you can go into rendered view and if you want to limit you can do Ctrl +B and do something like this and it'll create a render region. If you ever want to get rid of that render region you can come over into output and you can get rid of the render region over here.

**2:42:50** · That way you can see the other side. This way it will be a little bit more accurate.

**2:42:56** · And now you can just adjust your points accordingly. Now of course try and keep the spacing between them even and equal in distance. If you need more you can add more right? You can add a subdivision.

**2:43:10** · But again try and keep it even spaced out if you can. It does depend on the method that you use. And even if it's not even you can adjust for it in code depending on progress values and whatnot. But yeah, just for the most part, really up to you. And just keep adjusting. Okay, now that I think about it, I think the curve will actually have to be completely inverted, if that makes sense. Like an inverted small circle because we have to put it on the other side and putting it over here is too close. So, what I can actually do instead is probably give it the camera a huge offset. Let's go over here.

**2:43:39** · And maybe we can just do like Well, actually, sorry, let's start at zero first just to make sure that everything is where it's supposed to be. Cool.

**2:43:49** · Yeah. Okay, so both of these are at zero. Then now maybe we can give it some sort of offset. So maybe like 45 or something. And now it just starts from the other side. And yeah, we probably should have used an empty. I think I'm going to replace it with an empty. Or you can just like make it a little bit smaller. But yeah, now we can start from this side and scrub it like so. Yeah.

**2:44:10** · And this makes a lot more sense now cuz we're starting from the other side and looking really really far away. So this makes a lot more sense. Okay. So, I made the character also follow their the moving characters curve, which I'm leaving as a circle. If for some reason you don't want to leave it as a circle and maybe give it like some slight offsets here just for variation, you can totally do that as well. And if it ever bothers you to where you can't stand all these lines and stuff, you can just come over here and disable viewport overlays.

**2:44:38** · So, like everything over here just to, you know, hide some stuff. You can hit T hide that part and to hide this and then disable these as well. Control shift alt z is going to be the hotkey for the visual stuff in the viewport. So now we can have like a clean slate to work from. And again, we don't really care about this file in the sense that we're not going to export anything from it. So feel free to delete stuff and just prototype around. Again, for your camera, you can also check the different resolutions.

**2:45:05** · So, you can try like 1080p by 1920, a different aspect ratio over here. Flip the aspect ratio for mobile.

**2:45:15** · I don't know if I'm going to make a separate mobile curve or just add offsets to the original curve. That'll be up to you. Either way, you'll know how to do either one. But for now, I'm just going to stick with a desktop one and then possibly just add offsets for the mobile one. And yeah, you don't have to limit yourself to 1920 x 1080 either.

**2:45:32** · It's just how you want to design things and whatnot. Anyway, once you're done, you can select all your three curves.

**2:45:39** · So, I'm just going to select all them, holding control just to select them. So, make sure go into edit preferences and make sure you have this add-on installed. So, you can come over here and install from disk. It's going to be you can create a Python file and just copy the add-on that I give you over here, which I generated with AI and it just takes your objects and exports them as a 3GS curve. So, this will be on the Google doc. You can just copy this, create a Python file, and install it like any other Bl Blender add-on.

### AI generated Blender addon to export curves

**2:46:08** · So, with this installed, once it's installed, you can come over here, file, export, and curve to 3GS points. And make sure you select control points and not sample points. And then switch to JavaScript. Then you can just give it name it whatever you want. And then just make sure to save that after. And here I just opened the curve.js file. And you can see that it has the name of our curve. and all of it has been converted to 3JS points that we can use in our code. Okay, so the method that we're going to be using this time is gap scroll trigger.

### Using ScrollTrigger and Lenis to move our camera along a curve

**2:46:38** · If you've never heard of it, it's a very very common thing to trigger certain things to happen based on your scroll. You can see this is just a demo over here, but you can also go like on CSS code pens and just type in scroll trigger and you'll probably see a bunch of them. You can see as I scroll my scroll bar, the text is going horizontally and there's some animations and stuff like that. So when it comes to scroll trigger, it needs an HTML element to quote unquote trigger or track. So a lot of people when they use scroll trigger, they create these what we call dummy or proxy scroll areas.

**2:47:09** · So if I go into control shift I, this is a very popular website. You can see I actually do have a scroll bar here even though they overrid the original one. And if I come over here and click on the div content, you can see that as I scroll, it's actually translating an invisible div div that's overlaying here every so often. You can see the y value keep going going down. So every time I'm scrolling, there's like an invisible div that is like going down and up.

**2:47:36** · And this is exactly the same method we're going to be using. This is not the same method I used in my previous videos. You can see that there is no invisible div that is scrolling. It's just the experience itself. So, so like I mentioned, there's a lot of different ways to implement a similar functionality. And I don't like repeating myself cuz I covered this one in a different video. So, we're going to try this new method here. You might be saying, Andrew, where do we put it?

**2:48:04** · Didn't you say you like to keep your 2D ones separate? That's a DOM element. So, I guess we should put it in here, right?

**2:48:11** · Well, it's also kind of part of the experience. And splitting stuff up unnecessarily sometimes is also bad. For us, it doesn't really matter if we just put it straight into the experience. So, we can just come over here and we can just create a div. We'll just call it dummy scroll div or whatever you want to call it. Actually, I'll give it an ID instead of a class name. Not that that really matters cuz we're not really going to have much HTML at all. But yeah, this will be the div that we scroll. Oh my god, you're such a dummy.

**2:48:37** · If you go back to the website and you click on that DOM element, you'll see it's 13,372.2.

**2:48:43** · 2 pixels tall. I don't know how they came up with that, whether it's calculated or just hardcoded, but either way, it doesn't really matter. We're just going to do the same exact thing and just create a really tall one. So, you could create a separate CSS file if you want, or you can just put it directly in line over here. I'm going to start with a height of like a th00and.

**2:49:01** · So, let's just do like a height of a,000. Group word height like so.

**2:49:07** · Whoops, I forgot the what do we call what we call it? Quotes. And we want to disable pointer events on this div cuz we don't want to like click on it and stuff like that. So we'll do pointer events. And we'll also set that to no.

**2:49:18** · Make sure to move this div outside the canvas cuz it's not part of the 3GS. And oh, okay. Yeah, we need to have some empty brackets over here just so it's not bugging out the JSX. Let's place it like this. So now you can see that the dummy scroll div is underneath the canvas. So it's kind of like off into oblivion here, but we actually wanted to start at the same place as the canvas.

**2:49:38** · Now, because we're using this method, we actually have to change our CSS and we can no longer create overflow hidden because we actually need the scroll gesture. Instead, what we're going to do is just hide the scroll bar itself. And we're going to keep the canvas fixed on our page. But we should just be able to do overflow Y and just set it to auto and it should be fine. And yeah, so then we can get comment this out. And I I don't know if we have to explicitly set this, but I'm just going to set X2 hidden just in case.

**2:50:09** · Then we go back to experience. And you can actually style your canvas directly here. It'll style the parent div, I believe, if you style directly in here. So we can add some styles over here. And we'll do position text. That way it stays at the top.

**2:50:23** · Absolute is also fine, but fixes fix is more commonly used in in these kinds of scenarios just for semantic purposes.

**2:50:32** · And then we can do left zero like so.

**2:50:36** · Now if I refresh the page and go back the dummy scroll div should be on top.

**2:50:39** · Indeed it is. It's not spinning the full width. So we can do that. And where was the scroll bar wire? Where was that? So we can just come over here real quick and we can just set that to 100%. Oh, that's still not the issue. And I think it's because I think it's because of this right here because it's basically saying cut it out cuz we should have a scroll bar and now it's just it was like hiding the scroll bar for some reason. So okay, now we have a scroll bar and that makes a lot more sense.

**2:51:08** · So basically the entire thing is like just take the entire height and then chop off everything else. So instead of height 100%, we could also do like min height and this should be fine as well, but honestly it doesn't really matter. Now, we can just hide the scroll bar. And I'm just going to type that out. And I'm probably going to edit this out in the video so you don't have to watch me. And if I go back here, you can see that both of these are taking up the full screen and height now, which is great. I'm actually going to enable this just so we can have a frame of reference later and add that back in temporarily. Okay, so I think earlier we installed GSA already.

**2:51:38** · So now we need to install GSA React cuz they've got some useful built-in hooks for us that has some extra functionality. If you're a vibe coder, you don't really have to know other than it's just something to use alternatively. AI can help you just use a regular use effect and clean up that way. But we might as well just use it the correct way. So we can just see it right over here. Control back tick create a new one. We don't have to cancel our development server.

**2:52:05** · And we'll just do mpvmi and install gab/react. You'll also notice our orbit controls is conflicting with the scroll bar. So we can also just disable our orbit controls as well.

**2:52:16** · All right. So, let's get rid of that orbit controls. And now we can create a custom camera. So, I don't know where to put that. Actually, I think I'll just put it here cuz it's so tight. It's going to be tightly coupled with the scene. So, we can just put it in the root experience directory. It doesn't really matter. And I'll just call it custom camera. I don't know, whatever.

**2:52:33** · Call it whatever you want to call. And the entire idea is to get a point on the curve and make the camera position copy that curve. And the way we're going to do that is using get point at on the 3GS curve. So here you can see that it's a little bit different from get point but it still does have the similar issue that I mentioned earlier about uneven spacing. Like for example it depends again on the method that you use but let's say you have a curve like this a point like this and then a point like this and a point like this and this is one curve and this is your first curve and let's say your mouse on tick adds 01 0.1 increment.

**2:53:07** · Well, your camera is going to go over here on one tick and it'll look like it's flying faster.

**2:53:14** · Whereas over here, it's going to maybe go like somewhere over here on same one scrub tick, but it's going to travel farther distance, which means it's going to appear faster in your viewport.

**2:53:23** · That's just something to acknowledge and why I mentioned that earlier. Again, it's not a big deal. We can always adjust it in code, but just something to keep in mind. Okay, so let's do our AFCE just to create that real quick. And let's just control D get rid of that.

**2:53:36** · And the first thing we're going to need, I think, is the camera itself. And the way to get the camera itself very conveniently in React 3way is using the use three custom hook over here. It's a state object. And the state object properties includes the camera over there. So we can just deconstruct that from the hook. So we can do const and deconstruct from camera. And then we can set it equal to use three. Hopefully it finds import. It does. Nice. Just like so. And of course we also need the scroll progress, right? So, con scroll progress.

**2:54:07** · So, that's going to be the value between 0 and one like so. And we're going to set that to a use reference like so. And then we're just going to set it at zero cuz it's going to start at zero. You might actually have to offset that later. It depends on the curve. But for now, we're just going to set it zero. And the next thing we need to do is actually instantiate the use scroll trigger on once it gets onto the page. So, so in old days you used to use a use effect. Now, we're going to use a use gap. It has a little bit more built-in functionality, but you could also go with use effect if you want to.

**2:54:38** · And we're going to have an empty dependency array because this is only going to be initialized the first time custom camera is created. It'll never be changing for any other reason. So, we can just leave it as an empty dependency array. Now, if we go back to the docs, you can see we have to register use GAP and we also have to register scroll trigger. So we can just come over here and do it outside of everything. And we should be able to also just type scroll trigger here as well. Just like so.

**2:55:05** · Let's hit control spacebar to import that. Oh, that's already imported. And let's do this one same as well. And this one's going to be from gap/croll trigger. Okay. And basically the entire idea is when we scroll the div, we're going to update this scroll progress value. Now in order for us to use gap, we need to create an object for this. So let's change this to an object instead and we'll do this progress progress and we'll set that to zero at the current moment. Cool. So let's do that and we'll just do gap.2 roll progress current.

**2:55:34** · So if you're a vibe coder use reference creates an object where it's like current and then inside of your object over here it's your whatever you put inside. So zero. So that's why we have to do scroll progress.curren.progress progress pretty much, which is what we're doing here. And yeah, so now we can just do progress and we're going to set it to one. So we're just telling Gab go to one basically. We don't want any easing. We're going to let linear interpolation do that for us.

**2:56:04** · So we're going to do none. And then we're going to set up our scroll trigger like so. So I'll do scroll trigger. And we need to set a trigger. And that's going to be our hashtag hashtag. We can just pass in an ID here. So let me see what is that.

**2:56:19** · Uh, it's going to be id scroll div dummy scroll div. And I'm going to alt back arrow just to go back to where your last cursor is and alt forward as well. You can also come up here and hit those as well. So I'm going to be using those hotkeys as well. That'll be our trigger.

**2:56:35** · And we're going to have some starting markers at the top and top. And we're going to set scrub equal to one. So scrub means it'll ba be based on your scroll. Whereas, if you don't have scrub, then Gab is automatically going to play like a one second animation to scroll to the bottom for you. And I think by default, the bottom will be fine. And then just to show you what that is if you're new, we can also set markers equal to true. So, let's actually implement this now. Let's go back into experience. Well, I no, it's part of the scene. The camera is part of the scene. So, let's come over here and let's do custom camera.

**2:57:05** · Custom camera create it found it for us and just place it right. Of course, we're getting su is not defined, which is fine. And we can control spacebar and import gap from GSA just like so. And just to be a little bit organized, I'm going to alt up arrow that. Cool. And now you can see that our starting scroller and the trigger point is at the top. And it looks like our bottom is also at the top there, which means it will trigger all the way onto the bottom. I don't think that's I don't think it matters actually because we're not triggering anything else. But anyway, we can also just do that for bottom. So we can do bottom bottom.

**2:57:40** · And let's change this to the ending trigger. Just like so. So now you can see our start starts right at the moment. So it immediately activates as soon as it's mounted. And then we get to the scroller end.

**2:57:53** · And as soon as the scroller end hits the end at the bottom there, it's going to stop. So it doesn't really matter where you put those as long as you have some amount of distance between them. Like if you put the ending marker over here, it's effectively like setting the div to a viewport height of 500 instead of a th00and like we did. But now since everything is at the top and top and bottom bottom, all we have to do is just change the height and not worry about the marker positions. Okay, let's just get rid of that right now. Actually, actually, you know what? This is a component. I'm going to put in component.

**2:58:24** · I mean, it's not really reusable, but I think it's more of a component. It'll update the path for us, which is nice. Now what we need to do is update the camera on every frame because this internally is actually also using in a request animation frame. But if we're triggering the object update based on our HTML scroll position. So instead what we need now is to do the same thing for 3GS. And we can do that with the use frame hook. It's just a request animation frame. So you can see it's it's just this pretty much with a few more other features, but that's pretty much all it is. Let's just store it into a variable. So I'll just do con scroll.

**2:58:58** · I'll just call that scroll progress and current.progress just associating there. And now we can just get a point along the scroll progress which is determined by our gap that's updating it. Let's add our curve.js stuff into our components over here as well.

**2:59:14** · And one of the cool things about this add-on that I did not even ask it to do is that it created this thing here called create curves that literally exports an object creating key value pairs of the curved name equal to the curve data over here which is so cool. We don't actually even have to do anything. I didn't even prompt the AI to do that. It just did that for us. So that's super nice. What we can do just do now is let's curves right. It's a curves object over here with key value pairs to pointing to the curve using the the name that that we put over here.

**2:59:44** · And they call it camera look at curve. I don't like that it's capitalized. So let me just change that camera path curve.

**2:59:56** · If it doesn't bother you, you don't have to change that. And we'll just do camera path curve get point at like we said in the documentation over there. And then we'll just pass in the scroll progress position. So, let me Ctrl +B to get rid of that sidebar there. And now we should just be able to do camera.position.copy.

**3:00:15** · And we'll just do camera curve position.

**3:00:17** · So, camera is from this right over here at use three. And it's not working because it's the import doesn't didn't.

**3:00:25** · So, let's go back to scene.jsx over here. Oh, I just didn't save it. My bad.

**3:00:28** · And now it's saying curves is not defined. And that's because we didn't import it. I'm being stupid. So, oh, actually, we could just use exported curves. I didn't know they gave us an array there. Oh well, whatever. I'm just going to use a method cuz I already am doing that. So, let's come over here and let's type create curves. Create curves.

**3:00:47** · And let's import that. And we need to instantiate that. So, we'll do cons curves. We're going to use a use memo because we only want to create it once.

**3:00:55** · We're never creating these curves again.

**3:00:57** · Never ever ever getting back together.

**3:01:01** · And then we'll just call Well, I don't need that cuz it's one line. create curves the method over there that we got. And then we'll just have an empty dependency array just like so. And make sure to import use memo as well. And now if I go back and refresh the page. Oh my gosh, it's working. Hallelujah.

**3:01:17** · Hallelujah. Oh my gosh, it's working.

**3:01:19** · How easy is that, brother? Oh my god.

**3:01:22** · Bring me a real challenge, brother. Give me a real challenge. Now, you can see when we hit the bottom, we have an issue. It's not looping. So, how do we fix that? Well, we can easily do that using another package called Lennis.

**3:01:35** · Now, if you're into awardwinning websites, you've probably seen Lennis often. It's one of the most popular ones. And you can also implement your own custom smooth scrolling. It's actually not that difficult. Now, there's a reason I don't like using external packages as much as possible because they often change. But in this case, Lennis is just like such an industry standard for developers in this field. we might as well just hop on the bandwagon and use it as well.

**3:01:59** · So if we go to the docs here, we can see we just have to install Lennis and then we import React Lennis and it just wraps around our root and then we have some options here and one of them is going to be infinite. So I can just search for infinite and here you can see enable infinite scrolling. It's just going to infinitely scroll for us. Controll back tick. Let's uh I got rid of the other one. We can create a new one. MPI Lennis. Let's come back to experience and just place react lens over here. I might move this into the app level.

**3:02:29** · I don't know if I want to put assets yet or not. Sorry, I mean HTML DOM elements or not yet. So, we might actually move this up a notch if we want to. But for now, we'll just place it in here. And we can always just change it a little bit later. Set it to root equals true, which uses the entire HTML element rather than a specific DOM element. Speaking of which, just to say that you actually don't have to do flat equals true here.

**3:02:55** · You can just leave it as flat. You can set the options and that's also an object. So, we can just set infinite and we'll just set that true. And let's just make sure to control spacebar and import that from lens react. Now, if I go back and refresh the page and scroll up, something is happening and it's not working because what it's doing instead is going from 0.999, 0.98 all the way back to the original location rather than infinitely looping. So, it's going through the entire curve again, the wrong way. We can actually fix that by changing our scrub value to true.

**3:03:26** · So, let's go to our custom camera and instead of scrub equal one, we can just set this to true instead. Now, if I go back and refresh the page and scroll up, voila, we have solved our issue. So, scrub basically just adds a delay of when to catch up. So, if I add like 20 seconds here, you're going to see it's going very, very slow in the wrong direction. Let me just refresh the page and show you real quick. If I scroll down, you can see it's going the other way and it's taking like 20 seconds before it goes that way. True basically just means take that instantly go to that position.

**3:03:58** · It doesn't really matter about anything else. So technically you could think of it like it's literally teleporting through the wrong direction of the curve if that makes any sense. So it does feel kind of like a hack but at the same time it's also just a solution.

**3:04:14** · There's other ways to solve this infinite looping solution but this is definitely the easiest solution possible. Now before we move on we should always check the documentation and indeed there is something over here to integrate with GAP. Now, this is optional and just from my personal experience, it's probably not a big deal if we don't add this in. But the idea is to remove the internal request animation frame from Lennis and just use the Gap one instead cuz right now we have Lenus that has its own request animation frame loop running. Same with GSA, it's got its own internal one and then same with React 3 fiber through use frame.

**3:04:44** · So, this is just an optimization technique to get rid of the Linus one and also just to make it sync up a little bit more accurately. You can also if you want to get rid of the GSAP internal tech and just use one single one through the use frame hook of React 3 fiber and that would also be perfectly valid as well. And I think you can also alternatively get rid of the internal one in React 3 fiber and use your own custom request animation frame if you want to. That way for every single solution you only have one internal request animation frame that's synced across all these three packages.

**3:05:15** · Does it really matter? For most projects, it probably does not matter at all. But for the sake of clarity, since this is in documentation, we might as well do it as well. So, I'm just going to copy this over here. Let's go back into experience.jsx. And let's just paste that right in here. We might need to do some imports like use effect. So, empty dependency array. We're only doing one over here. And now we just need to lenice ref over here. So, we just set ref equal to the lenus ref just like so.

**3:05:44** · And we probably need to import gsub as well. Yeah, we do. So let's import gap from then let's import use ref from react as well. And then we have to set auto ref inside of options also to false. So we'll just set that to false.

**3:05:57** · Oops. Sorry I keep doing semicolon. And now if I go back you can see it's the same exact result, but now we're just sharing the ticker with the gap one instead. Now if it's a little too janky for you, you can actually improve the smoothing by improving the linear interpolation factor. So that's also here. So you can set a lower value. I think by default it'll be 0.1. So you can try something like 01 or something.

**3:06:20** · And now you can see, wow, it's like super smooth and the sensitivity is like really low. It's like slow motion at this point. Now you'll still feel the camera edges like where it changes. It still feels a little clunky and that's because we're not using linear interpolation on the camera position curve itself. Right? If I go to custom camera over here, you can see we're just getting the point. We're not linearly interpolating there. So, we'll fix that in a little bit, but let's for now get in the architecture and then fix that jankiness in a little bit. All right, let's undo that. I'm just going to leave it at 0.1.

**3:06:51** · So, let me go back to custom camera and I want to talk about the issue we have right now. Right now, this scroll progress value belongs to custom camera, but we need the scroll progress value in order to know where to trigger stuff in our models. And also, our moving characters also need to know the scrolling progress. So how do we do that? Well, we would have to put it to the parent component, right?

### Upgrading scrollProgress to global store with Zustand

**3:07:15** · So instead of this over here, we would have to extrapolate it in to scene and then we would have to pass it in as a prop to the children of scene. So we'll just do scroll progress like so, right? And then everything else that needs it, I feel like I think everything needs it depending on your animation. So we'd have to do something like this. And then internally custom camera we would just do and we don't actually have to target it. We can just use like a empty and then like the on update function and update the scroll progress over here.

**3:07:50** · Scroll progress current blah blah blah blah blah. Now is that fine? And yes, it's perfectly fine to do that cuz that's only one layer of digging. This is kind of messy and a little bit redundant. So instead, we're actually going to take this and set it to a store instead of doing this prop drilling.

**3:08:09** · Now, I wouldn't consider this prop drilling because it's only one layer down. But let's say one of your models has another model inside this model.

**3:08:17** · Then you'd have to drill it down to that one as well. Again, that will probably never happen for this project. But either way, let's just do it the professional way and use a global store.

**3:08:27** · So, let's just get rid of that. And let's also go into custom camera. And we don't have to repaste this here cuz I'm going to place it in the global store instead. So for to create our global store, we're going to use zustand over here. Zoo standpvi and install that. Make sure it's installed.

**3:08:46** · And once it's installed, we can create our first store. So since our store is global across our JSX or HTML stuff as well as our 3D stuff, we can just put it directly in the source. It makes semantic sense to place it there instead. We want to follow best practices. So we can use your naming convention which is typically use what it is and then store after. So it's like your grocery store or whatnot. So this one is going to be progress. So I think we can call it use progress store. Use progress.

**3:09:15** · Actually let's also call it use curve progress store cuz we also want to attach the curve as part of the stores as well. So let's do use curve progress store.js JS like so because we don't want to create the curve every single time, right? We don't want to call create curves every single time. I know we could just reference the array and that would be fine as well, but we might as well just put curves as part of the story as well. All right, so let's come back over here. And now we can just follow the documentation and copy this over here.

**3:09:45** · Now to all the vibe cutters, this looks a little bit scary, but all it's saying is just like create a state here. And then these functions are saying take that original state and whatever that state is, set it to this new thing over here, which is the current state bears value plus one. So every time you call this, it's just going to take this and add one to it.

**3:10:05** · And this one just resets the state back to zero. So remove all bears. So same thing, we can just copy and paste that.

**3:10:11** · And we can hit F2 here. Copy and paste that. So we don't have to type that out there. And I think one thing I want from custom camera is this over here. So we can just paste that in there. And I don't actually really like how I have to go inside. We don't actually need a second file. I don't know if I want to do that or not, but whatever. It doesn't really matter. Just format your code how you want to format it. For the curves, let's just do create curves. Create curves. And now we can just reference this through the store. And of course, we need a scroll progress value. So I'm going to do scroll progress.

**3:10:43** · I'm going to set that to zero. We need a setter to set the scroll progress. So, we'll just call this set and paste that there and get rid of this just like so. And we're going to pass in a value here that we're going to update in the front. So, we can call this value. And then over here, we can just set the scroll progress value to the value. So, scroll progress over here. And let's just change this to the value that we're going to pass in from our front-end React code.

**3:11:11** · So, just for all our vibe coders out there, feel free to skip ahead like 10 or 20 seconds.

**3:11:18** · Instead of a scene having the progress value and going down to the models, each one like this, and then the custom camera updating that value that goes back over here, updates that reference, and then the reference is passed down to each child. So, instead of that kind of flow where it's like here to the one that updates, it goes back there and then down to the other children that don't update it. So like the models and stuff like that. What we're doing right now is just a scene and then we have the custom camera that updates a store and this is a global store.

**3:11:51** · And then all the models and stuff like that just point to the store instead just like so. So it's a little bit cleaner that way. Again, for this project, it doesn't really matter. It's not considered a bad practice just to do this way cuz it's literally just one really just one prop that's where one level of prop drilling.

**3:12:09** · It's only when you get like multiple layers deep and things like that where the stores become necessary. But I'm still doing it this way because it's cleaner. So now we can just reference everything in the store instead of creating it ourselves inside the component. So we can just do const curves and we'll copy use progress store over there. And in the past I do want to mention that I think I did deconstruct by accident when I only needed a few things. Now, this is technically a bad practice because it'll trigger a rerender anytime anything in the store updates when you do this.

**3:12:40** · So, you only want to select the one that you actually need. It's okay to do this if you need like three or four and just want to save time and blah blah blah or whatever. But when you only need a few, you want to use their other way to do it. Just just taking the state object and selecting the state objects property that you want. So, I just want the curve object property. And I don't know why this isn't Oh, it's cuz we didn't export it.

**3:13:04** · Oops, my bad. Let's do export and save that as well. And now we can control space right now find it. We need to set the scroll progress, right? We are updating the scroll progress here. So we also need this down arrow over here and do set scroll progress. We can use the same exact name because it's scoped inside of our component. And we can just paste that in there like so. Thick. Now we could remake a dummy object here instead of using the one in the store and then just sync up the dummy one to the store.

**3:13:33** · That's there's nothing wrong with that either, but we could also just get rid of it. Since you already know how to do it this way, we might as well show you the way to get rid of it as well. Each either way is fine. It doesn't really matter. So, we can just create a empty dummy scroll trigger. We can pass in a trigger going to be our dummy. Well, actually, we can just copy and paste this right over there. Cool.

**3:13:54** · And we can actually get rid of this. I don't think we need this anymore. Then built in into scroll trigger is an on update function. So when the scroll trigger updates which is based on our scroll do something every time and you can there's a self referencing object.

**3:14:08** · So it references itself internal state.

**3:14:11** · You can kind of imagine like scroll trigger also kind of has its own store inside that we're referencing. And we're just going to set that self progress value to the one in our store. So set scroll progress and we're just going to set it to self.progress. So you can imagine internally there's like some store in scroll trigger that's tracking its own progress from 0ero to one.

**3:14:32** · That's how it determines like duration and where it is and all that kind of stuff. So we're just setting that as we scroll from the top to the bottom. It's going to go to 0 to one. And we're just determining that on scroll progress. Now this time we can actually use another method that comes with just called get state. This way it won't trigger rerenders when the scroll progress is changing. So we can come over to use curve progress store over here and we can do get state. get state and the state we want to get is the scroll progress. So we can just copy and paste this over here. Oops. And this directory is wrong.

**3:15:02** · So let me go back one just like so. And I'm missing create here or scroll trigger. And if I go back everything should be working. Yeah, it's looping properly. So that's all good to go. So let's just do the same exact thing except we now need to get the look at. So we just paste that over there.

**3:15:20** · Camera look at look at curve position. I don't know what we actually named it.

**3:15:26** · Let me go back to curves.js and camera path curve. Moving characters curve. I'm just going to camel cases and camera look at curve. Yeah. Okay, cool. Again, it doesn't really matter. Maybe I'll make it all lower case because it looks better, but uh it doesn't really matter.

**3:15:41** · Cool. Same position. We don't have to change anything. And now we can do camera position.

**3:15:47** · Instead, we'll do look at look at.

**3:15:49** · Sorry, it should be capitalized. And then we just put this one instead.

**3:15:53** · Sweet. So, it looks to be working. It is looking at something and it does seem to be following our pattern except we gave it an offset. Well, at least I gave it an offset when I was doing it. So, if I go back to the Blender file here and click on the camera and click here, you can see I give it a plus 45 offset.

### Basic camera offset formula

**3:16:10** · Since this is based on the original frame, I guess it's like a 50% offset.

**3:16:14** · Same with the cube. Cube. You can see there's no offset. Sorry, I don't know why I said same width. Only the camera has the offset. So, let's do the same thing with the camera. Let's give it an offset. So, we'll give it directly to this one. We'll just do const offset scroll position. I mean, offset camera position might be better. That's Yeah, offset camera position.

**3:16:38** · Scroll camera position. Sorry, I'm out of breath because I just ran up the stairs. And let's see. Offset blah blah blah. Yeah. And then we'll just do equals this. And we'll do plus 0.5. Now, we can't just offset it at 0.5, right?

**3:16:53** · What if we're at like, let's say, 0.8 and we add 0.5. We're going to go to 1.3 and that doesn't exist. So, cause a crash. So, instead, what we do is modulus / 1. And this will keep it within the range of 0 and 1. That is math coming in here, but it's not too scary math. It's just basic math there.

**3:17:13** · And we can just use that offset scroll camera position instead of our scroll progress position. I think I had 0.45.

**3:17:22** · It doesn't really matter. I'm just going to do 0.5 and see what that gives me.

**3:17:25** · And if I refresh the page, voila. It looks like exactly what it looks like in Blender. I might have did a slightly different offset than what I did in Blender, but it doesn't really matter.

**3:17:34** · And if I go in Blender, like, take a look. It's It's pretty much the same thing. Well, it is the same thing.

**3:17:39** · Sweet. So now, every time you need to make an update, all you have to do is go in Blender and well, we should rename this cuz our plug-in will automatically rename it in the JavaScript file to match what we have in code. But yeah, every time you want to make a change to something, you can just update it. And when you're done, just file and export curves. Make sure you select all them because we putting all them in a single file. So select all of them, export as curves, and just replace your curves file. And you don't have to do anything else. Okay. Now, you might be asking a little question here.

**3:18:10** · Why are we still using scroll trigger if we're not actually triggering any HTML elements for it? I'm sure Lennis probably has some sort of built-in self progress that we can use to set scroll progress as well, right? We don't need to use scroll trigger for that. It's kind of weird that scroll trigger we're registering it inside of a child component instead of the hierarchy component. Since we only have to do it once, it would make more sense to put it here, right? If you have both those questions, congratulations because that's exactly what we're going to do right now.

### Changing from ScrollTrigger to only Lenis

**3:18:37** · If I go back to the docs on Lennis and I look for progress, you can see indeed there is a scroll progress from 0 to one. And if you come back down to events, you know, like window.adde eventlister, there's also a scroll event here that we can listen to and when Lennus is scrolling, update the scroll progress. That way, we don't need scroll trigger and lens smooth scrolling. We're still probably going to use scroll trigger later, but not for this dummy div. So, let's do control P or command P and let's just say that we're back to experience and we can register this here. Actually, we could register it for the app.

**3:19:07** · I think I might register it for the app later, but whatever. Let's just put it here for now cuz we don't want to think too much. Who wants to think when they're coding?

**3:19:17** · Like, come on. Let's be real here, guys.

**3:19:19** · Cool. And let's see. Set scroll progress. We only need curves in here.

**3:19:23** · So, we can move this over into experience as well. Just like over here.

**3:19:28** · Let's control spacebar to make sure this is imported. And in this use effect when the component mounts. So for the vibe coders when we switch an HTML component or add one we call that mounting a component and then when we remove it we call that unmounting. So this is what we call a cleanup function here. Basically after it unmounts what do we do? It's not going to unmount for a while. I don't even know if we're going to do anything that unmounts in this video. I might but that's what this is here just for the vibe coders out there.

**3:19:56** · So let's create a function here that syncs the scroll trigger to the lenus one. And I'll just do const sync scroll sync scroll equals and we want that event object that comes with scroll. We'll do scroll trigger update. So we sync it up to the lenus scroll. And then we'll do the set scroll progress equal to the event object and progress which is by default part of Lennis.

**3:20:18** · So we can do lenis ref.curren current do on and we pass in the scroll event and we just pass in sync scroll just right over there and then we can clean it up and remove that on leave and we just change this to off. So instead of window add event listener and window remove event listener it's on and off for Lennice and we can get rid of use GAP. Well actually no we can register it here as well. I'm just going to import that and then over here we don't need this so we can get rid of that for now.

**3:20:47** · Now, if I go back and start scrolling, it's still not going to work. And that's because Lennis is not being instantiated once the experience starts. So, experience starts and then there's like a tiny little blip. And then because we have an empty dependency array, it actually never gets run properly after that. I'll just show you. If I console.log this console.log like so, and refresh the page, you're going to see undefined. Now we see it twice because we're in uh strict mode.

**3:21:16** · But you can see that's why it's never going to fire because it never actually gets instantiated with our grip. So what we can do instead is replace this with a use state. And we'll just set it to null because it's an object. And we just want the Lennis and then set Lennis. So set Lennice and we'll set that to a state.

**3:21:32** · So once it goes from null to actually having an instance, we will re-trigger this. So we can put that in the dependency array so it knows how to do that. And then the reference will now be set lenus instead. And let's make sure use state is also imported like so. And we no longer have lennis ref. So we can get rid of that lenus. It should just be lennis over here. Let's just make sure lennis. Okay. And then we just we don't need current anymore because it's not we're not creating a current object.

**3:22:00** · And now if I go back and refresh the page, you can see that it works just like before. Now there is one issue that I want to talk about. If I go into mobile view here, you can see that it is basically pinned to the value. It doesn't loop infinitely. And that is right over here. If you search up infinite, you can see we require sync touch equal true. And we can come over here and just paste sync touch equal true.

**3:22:29** · And now if I go back, you can see that it infinitely loops properly. Don't worry, we'll cover all the responsive issues later, but I just wanted to mention that right now if you wanted to. I'll also say if you want to test on your local device, you can go to package.json.

**3:22:43** · And let's go and cancel our development server. And you can do vit-host and this will put it to your local network. And as long and as long as your phone has the same network, you can just go to this URL and you can view it on your phone. All right, sweet McGee.

### Basics of lerping and implementing linear interpolation for smooth camera movement

**3:23:01** · Let's go back and add some blur brings so we get that buttery smooth. So, let's go back to custom camera. What am I talking about right now? For those that don't know what linear interpolation is, there's a lot of different formulas it is. But let's say you have distance over here and you have your time and your request animation frame or use frame in this case is continuously running, right? So, as time increases instead of just linear doing it, which is what we're doing right now. Now, the smooth scrolling is also adding some amount of lurping to it. Right? That's what we call lurping. So the camera is actually also being lured itself.

**3:23:32** · But we can also just do it with the camera position itself. And we also want to do it with the camera target. So what it looks like is imagine this is point your starting point. This is your ending point.

**3:23:44** · Distance is continuously getting closer.

**3:23:47** · So we can assume I guess this is like closest to the next point. Instead of going like that, it's going to slowly approach your target distance over time.

**3:23:57** · Well, now that I think about it, this is a terrible drawing graph, but this is kind of the idea. And of course, there's different kinds of easings and different kinds of graphs that you can do. But the whole idea is like target position and then let your mathematical function calculate the distance in between your your target and you just have to update the target one. Okay, so let's go.

**3:24:12** · Uh what we can do is come over here and we do con target position. target position and of course you already know I don't know how to spell it's going to be a use ref and it's going to be a vector 3 so we're probably going to import all from vector 3 so let's see what is it three dot vector whoa shisa dot vector 3 and

**3:24:36** · we're just going to set it to 0000 just like so and we also want a target look at because we're also going to smooth those rotations and let's make sure to do it right so we need new here and let's control spacebar to import alt S3 is from three which I didn't do but whatever. All S3 as three from three just like so. Oops. Sorry. It should be lowerase. Now we also need like a current rotation or in this case I guess we could call it a current look at because target position we have a current position which is literally just the camera itself.

**3:25:07** · But for look at we don't have a current rotation anywhere anything. So let's do come over here and let's do current look at as well.

**3:25:15** · Current look at. Sweet. So let's just combine those two together just for a nice grouping over there. Sick. Now we want to get the point still over here, but we want to use a second parameter and change it to our target positions.

**3:25:28** · So here you can see we have get point at and then we have an optional target. So instead of mapping to our original just position copy and stuff like that, we're going to put it into the target vector and those targets are over here. So get the value, put it into our target position. Same with our target look at.

**3:25:46** · So we're going to place our target lookout over here. And then we both need dot current here because they're use refs. And now we can just do the lurping together. So cameraosition and we can just use dotlurp over here. Target position current over here. And we'll have a loop value about 0.1 over here.

**3:26:02** · And we need to do current look at now current. And we also want to lurp this to the target look at current current.

**3:26:08** · Also let's just set a value of 0.1. If you want to abstract this into a variable, you can. That way you don't have to change it in two places. We don't need copy anymore because it's looping to that position. And we want current look at dot current over here.

**3:26:21** · Just like so. We can get rid of these variables because we don't need them anymore. So just so if I go back, let's just take a look. And wow, it's working.

**3:26:33** · Super cool. And everything is a lot smoother now. So again, if it's a little too smooth, you can increase this just a little bit. You know, play around with the loop factor however you want. Now, there is one issue. When I refresh the page, you can see that it kind of has like this jump. And that makes sense because we start at progress zero and then we add the offset to five. So it's linearly interpolating between 0 and 0.5 really really quickly on the first few frames. So what we can do is just check on initial. Like if we're initialized, just copy the location.

**3:27:00** · Don't actually lurp to that position just for the first few frames. So we can do const is initial lurping. And we would set that to true by default because it will be every single time this is loaded. I think maybe in the future we might handle this from an intro animation rather than over here. But it doesn't really matter. We can just fix it now.

**3:27:22** · And now we can just check in these frame over here right after we get the positions. If the initial is looping current, if it exists, that means it's the first few initial things. Then we just do camera.position. Well, I guess we shouldn't have deleted all that other stuff because we could have just copied it. So, target position.curren current.

**3:27:41** · And we both want the camera look at and current look at to be the same target.

**3:27:48** · So, where is it? Where is it? Where is it? Oh, it's right there. Sweet. And control D just to select the next instance. So, both of these start at the same. And then this one starts at wherever that starts. Okay, let's see.

**3:27:59** · What do we need? Uh, camera. Look at.

**3:28:02** · So, we don't need copy here. Current. We need to replace this with current opposition and copy. Yeah, both of them look at the target. Look at if we have any areas, we'll figure it out along the way. Let's just refresh that page.

**3:28:14** · Oh, and voila, it works. How cool is that? Now, we should probably add a guard clause here. We don't want to execute anything after this. Now, we kind of already overrid it, but this is just to be safe. And then we should also probably it's no longer initializing.

**3:28:30** · So, we should set this equal to false.

**3:28:33** · So, this only runs first on on like the first frame. Sweet. And now we have no issues with that. Okay. So, the next thing I want to do is give it a little bit of offset because right now when I stop scrolling, it kind of looks like I'm just looking at an image. So, what I want to do is like make the camera rotate a little bit and maybe even move the position a little bit as I move my mouse as well. So, the way to do that, well, we need some sort of mouse input.

### Implementing camera offset

**3:29:00** · Now, in the past, in my previous video, I did window add eventlister and recalculated the normalized coordinates.

**3:29:06** · I just realized you don't actually have to do that because it's right here and you can just get it from the use three hook. So they conveniently did that internally for us. So we ain't even got to do the hard work, brother. We we can just come over here and just do pointer.

**3:29:20** · Now we don't have to do all those window event listener stuff and everything like that. Anyway, when it comes to window parallax, there's a lot of different ways to do it. Like imagine this is my web page over here and this is like my camera 3D camera. The most common way is if I move my mouse to the left, the camera will rotate to the left. And if I move my camera up, it'll rotate up on the X-axis. The other way is where you just invert it where if you move your mouse up, the camera goes down. And that's also fine as well. There's also ones where it just like directly goes there, kind of like how your eyes would go to the corner.

**3:29:50** · So there's a noticeable tilt because it's kind of like if you whip your head back and look up to the left kind of thing. The most common one is just doing it along the axis. So, that's the one we're going to be doing. There's a lot of other ones that I didn't mention, but those are like the two common ones. Now, we do have one issue. If the camera is looking at a target, right? How do we give it an offset? If you know vector math, it's actually not too bad. There's functions in 3GS that make it really helpful.

**3:30:16** · You can get where the camera is pointing at and then also do a directional up vector. And then when you take the cross productduct of this, well, what you get is you get the right vector. Sorry, this is kind of sloppy, but this should be direct up and down. So now you know the camera's local axis all the time just by taking the cross productduct and then you can just move it across left and right across there. So now while the vector math isn't too terrible, it's actually easier just to wrap it in a group. So we can just like demonstrate that with an empty.

**3:30:46** · And the empty will be the thing that's following the curve while we're applying the offset to the camera. So, if we can just imagine that we parent it to over there and we move this over here, we don't really have to care where it's looking at. The group can look at the camera and the camera's still not looking at the group, but it's still operating from its own local axis.

**3:31:09** · So, as long as we have the offset, it doesn't really matter cuz the group is doing the look at for us, not the camera anymore. So, this is just simplifies it a little bit more. So, let's come here and let's add a perspective. Well, let's add a group first. And let's inside add a perspective camera which will come from React 3 Dre. Let's add Oh, sorry.

**3:31:29** · Let's add a Whoops. I don't want that.

**3:31:32** · Just there. Let's make it default so React Fiber knows this is our camera that we want to use. We're going to give it a ref called camera ref for sure.

**3:31:41** · That way we can access it. And let's do the same thing for the group because we definitely need that. And we'll call this camera group ref. Let's hold alt double click. So we have two over here.

**3:31:51** · And let's just shift alt down arrow these two. Hold alt control +v just to paste that. Get rid of these right here.

**3:31:57** · Just like so. And instead of let's see camera we want camera group ref to do all the look at and lurping for the position. So let's just paste that. And then current because now it's a reference instead of the camera that we deconstructed over here. Cool. And we need one more thing which is the current pointer right because the pointer becomes the target. This pointer value becomes the target.

**3:32:24** · So oh I should also mention this is normalized coordinates which means if you move your mouse to the left it'll be negative 1. To the right is negative 1. Sorry positive one.

**3:32:33** · To the bottom it'll be one and to up it will be negative 1. Well actually sorry I think bottom is negative one and up is one. I don't actually remember but it doesn't really matter cuz we'll find out anyway. So what we need then is a current pointer that lurps to the target pointer which is just this over here. So we can just come over here shift all down arrow here and we call this current pointer current pointer. Actually you could just use an object. You don't have to use a 3GS object here.

**3:32:58** · Like if you just wanted to do an like a X0 and a Y z like if you're happy with that you can just use that. But since this is here I might as well just use that.

**3:33:09** · Doesn't really matter. I don't know if there's much of a performance difference or not. And current pointer, let's see.

**3:33:16** · So here we just want current pointer current. And we want to lurp to the new pointer. And I'm just going to give it the same value as the other ones. We can always change that later. We can just directly do the camera ref and apply the offset set current pointer. Uh let's just copy this to save some time. X.

**3:33:35** · Let's just shift alt down arrow to do Y as well. And let's have some to prevent it from being too sensitive. Let's just choose some arbitrary value. And then Z.

**3:33:46** · We're not changing the position of Z. So we can just get rid of that. Same thing with rotation. It's going to be the same over here. All right. Let's just go back and see what we get. Uh let's see. Uh it's Yeah. Okay. We have to flip rotation. Sorry. This should be Y and this should be X. And when I go right, it's going left. And when I go left, it's going right. But down and up is working fine. So, because I'm rotating, Y is up and down, which means I'm rotating along the Y- axis when I go left and right. So, it should be this one over here. Yeah, negative of the left and right. And now it's working.

**3:34:15** · My camera is Let me see where it's So, we should just be able to add math.py over here. So, let's put in the parenthesis.

**3:34:24** · And let's just add math.py over here.

**3:34:27** · Hopefully, that solves it down. See, this is the inversion one. Um, if you like that, you can keep it, but I'm not going to do that. I'm just going to make that negative. Cool. So now when I go up, it's going up. And when I go right, it's going right. And of course, I feel like it's a little bit too strong. So we can just put this over here. Of course, if you want to extrapolate this into a variable as well, you can totally do that. Now, you'll notice if I refresh, it still is flipped 180 on initial frame load. So we can fix that as well into our initial looping over here. And let's do camera. Well, this Oh, sorry.

**3:34:58** · It actually just be the camera ref cuz that was the one that was effing up. So camera.ref. ref.curren.rotation go math.py math.py 180° and then zero.

**3:35:15** · So now when I refresh it should be fine.

**3:35:17** · Great. It's fine. Okay. So we should probably address the elephant in the room. The starting position is not where I started in Blender and it's not where I started in 3GS either. So how do we fix that? Well, we all all we have to do is just select a point, hit N over here, go to our item, and make sure to take a look at the control point where it is, and we should look for the global space.

**3:35:42** · So, just make sure to take a screenshot of this. So, over here, this is my camera path curve, and over here is where I start or I want to start. So, I'm going to select that point and just take a screenshot there. If you can memorize it or if you want to just copy and paste it, you can totally do that as well. or you can leave your Blender file up and that's totally fine as well. And now we want our camera look at curve and this is where I start. So if you want you can make a slight adjustment to the point just so it's right where you need it to be and so on so forth. This is really not a big deal. Cool. Same thing.

**3:36:14** · I'm just going to take a screenshot of this just like so. Now I did make an update to the Blender add-on. So we do have to reexport it. But if you're watching this video you don't have to reexport it. So anyway, it will just be as part of your export anyway, but I'm just going to reexport it. And again, control points. And if you ever have issues with Blender add-ons like disappearing from your add-on list in edit preferences, you can always just directly go to your Blender. And I have a lot of other versions installed still, but for backwards compatibility.

**3:36:44** · But then you come into scripts, you go into add-ons, and here's the add-on we installed. You can make the adjustment here and delete it here. And then refresh your Blender to uninstall it as well. That way, if you ever have issues with this menu, like it's not showing up, it's not installing, you can there's another way to handle that as well. So, if I go to the new export with the new Blender export, well, you already have this cuz you'll have the new one. So, if you take a look at the new export, well, if you're watching this video, you probably already have this. There's this thing here called a start index.

**3:37:13** · And we can just select that and it will set that point as the starting one and then just shift all the other points. So down here you can see create curves has updated to slice and shift the points to our starting point. So if this is becomes the starting point then all of these are basically sliced out and moved over there and everything is shifted pretty much. So I guess we didn't really need to screenshot. We can just go back cuz I don't want want to look at my screenshot. I'm just going to select the camera look at curve and I'm just going to select this one. We actually don't have to move it but just look for 6.8 6.7 and so on so forth.

**3:37:46** · Again, the axes are slightly different. So, we can just make sure to keep that in mind. So, camera look at curve, we're going to start at 6.8577.

**3:37:58** · So, it's going to be this one right here, which is conveniently almost close. So, start index will be one here cuz array start at zero. So, it's going to start at one over here. Moving characters curve. Let me just check that one as well. It's going to be over 7.9912.

**3:38:13** · So, it's going to be this one over here.

**3:38:15** · So, we can start at index two over here.

**3:38:18** · And then for the camera path curve, and then for the camera path curve, it's on the other side. So, it's going to be at -4.7. Let's just look for 4.7 somewhere.

**3:38:27** · And it's all the way down here 12 here.

**3:38:30** · Cool. You could also update the add-on where you can like pass in a specific point and it'll find that rather than choosing an index, but whatever. It doesn't really matter. You can also ask AI to manually shift it yourself if you want to, but since we have the add-on, we might as well just use that. And of course, now that we have the actual good starting positions, we don't need our offset anymore, if that makes any sense.

**3:38:49** · And you can always, if you need an offset, you can always just bring it back, right? Play around with the values. We might still need a slight offset, but for now, we can get commented out. And then the target might also need a slight offset, especially if your points aren't in correct areas, but it doesn't really matter. And instead of using offset, scroll progress position, we can just use scroll progress position, just like this one, cuz we didn't have an offset for that. And now if I refresh the page and take a look, yeah, it starts where I wanted to start looking at the winter scene first.

**3:39:18** · Again, remember the offset doesn't have to be constant. You can change based on the scroll position the offset at any given point. Like like if the scroll progress position is like less than 0.2, greater than 0.1 or something, then change it to like 0.15 offset or something like it doesn't have to be a constant offset, but you know how to do that, so I'm not going to waste your time showing you that. Yeah. So, I think we're good to move on to finally moving our models along the curve as well.

### Moving models along curve

**3:39:44** · There is one small issue over here. It's not really a major issue, but over here, we set the camera FOV using the prop over here. Not that that's wrong, but since we already created a camera here, we might as well just set the FOV here instead. So, I'm just going to set FOV, and I'm going to set that to 50 over here. And I'm going to get rid of it over here. Does it really matter? No.

**3:40:07** · But since we're creating the camera, just do it here, I guess. Okay, sweet.

**3:40:10** · So, now we can just go to our models.

**3:40:12** · And let's just do our moving characters first. And by the time we're done with moving characters, I feel like you could probably figure out everything else for the rest of the models and then I'll talk about some other stuff and finish up the video. Okay, so we know we need scroll progress because depending on where our scroll progress is, we want to move certain characters. So, let's just copy this from let's see, experience.gsx.

**3:40:35** · Oh, sorry. This is set scroll progress.

**3:40:37** · No, we don't want set. Well, we can just use the same format anyway. Let's paste it here. Ctrl spacebar to import that.

**3:40:44** · And instead of set scroll progress, we just want scroll progress. I don't actually remember what I named it in the store. So, we can just check right here.

**3:40:51** · Yeah, we just called it scroll progress.

**3:40:52** · So, this is fine as well. Cool. So, now we have access to scroll progress. And inside here, we're just going to create our own use frame. Now, in the past, I think I falsely said that use frame will run multiple request animation frames, but it actually doesn't. This just points to the same one that's happening in our entire canvas one. So, just because we have a used frame over here and a used frame over here does not mean we're running two separate request animation frames. They actually point to the same one internally. So, yeah, I was wrong in my previous videos.

**3:41:23** · And anyway, we can import that from reactive fiber.

**3:41:29** · Of course, we also need the curves. So, let's shift alt up arrow or down arrow.

**3:41:33** · And let's just control Whoops. Let's just control D to select the next instance and type curves. Sorry, I activated my Chinese keyboard again.

**3:41:40** · Now, let's just get we can just polish this up later, but let's just get a point on the curve. So, let's just copy this and we call it moving characters.

**3:41:48** · Moving characters curve like so. We don't have a target yet, so let's just use the direct scroll progress. And instead of moving the entire group of moving characters, we only want the winter ones. So, winter front character, right arm, and left arm. So, just to show you that, if I hit this, you can see it's my moving character, front ar, front character, left arm, and right arm, just like so. And we all want this as part of the character, just like so.

**3:42:16** · Now, now that I'm thinking about it, if we wrap this in a group, we might have an offset issue because it's not at 00 0. I don't know yet, but let's just uh let's just hope that there's no issue there. So, let's just wrap it in a group. And we'll just give it a ref cuz we need to refer to it. And we'll just call this winter character front winter character would be better, but whatever. I don't care. And uh yeah, let's just close that up. And let's just copy that group. Let's just put it on the bottom of winter over here.

**3:42:46** · Now, our other winter stuff is not here. So, let's just make sure to copy all that winter stuff. Oh, no. Those are the winter side characters. So, that's fine.

**3:42:56** · Yeah. Okay. This is the only thing that's associated with this winter. That winter is for the side character. Now, we just need to import used ref, of course. Import that. Like so. And we're going to do const winter winter character front. Sorry, I was gonna and let's give it ref after. Just like so. And now we're just referring to the front character here. And we should just be able to make it move. So let's come over here. And we need a guard clause because it probably won't be rendering on the first frame.

**3:43:27** · So it might throw an error. If it doesn't exist, just return it. And now we can just docurren.curren.

**3:43:36** · position and we can just dotcopy the point which we need to create con point equals curves just like so. All right, let's refresh that page and see. Okay, the body is gone. There's two arms still there. So, either I duplicated the arms and need to change that or not. Let's see if we ever see it. Okay, at least we see something and it's just like into oblivion. Do we ever see Yeah. Okay, we see an arm and we see the body. Um, yeah.

**3:44:08** · So, this is the group issue that I'm talking about. Basically, the idea is like when you wrap it in the group, the position offsets are now relative to the group itself. So, the easiest solution is just to offset the group position, you can use a second group inside here and offset it, or you can just reset everything to zero itself and then add your own manual offsets, which is what I just did. You can just watch for now. I'm going to show you a better way. And you can see that it's now in quote unquote a correct position given its failed offset values.

**3:44:37** · In any case, this is considered bad practice because you don't want to keep manually changing stuff even if it works. So, let's fix it up in Blender first and then we'll rerun our script and then everything will be good to go. Okay, so sorry. I am such an idiot. We should not have deleted our empties. If you had empties, try and see if you have one where you have your empties back.

**3:45:02** · That way you don't have to well actually no several sorry that probably won't work because we probably changed a lot of stuff but anyway everything that you want grouped together just parent it to an empty. And what we're going to do is for every single one sorry let me just uh let's just make sure yeah for everyone make sure this is the active object P. And with the empty selected and then we're going to hit alt G and alt R to reset everything. Well, alt R wouldn't do anything because it's already no rotation on the empty.

**3:45:31** · And then let's go to the outline over here and hit period key just to jump to it.

**3:45:38** · It's right there. We call this winter front character. Front character. And let's right click, select hierarchy. So select all the objects and let's make it face the negative Y direction. So let's just well don't select the empty just the object itself. And now with all them selected, control A and apply rotation and scale. So now when I click on it, you can see that the rotation and the scale are both in one. Scale was probably already applied, but now rotation is also applied. And we don't want to apply location because we want to keep the origin points that we set originally.

**3:46:10** · So that way we can pivot over them. I want to repeat the same exact process with all the other characters. And I should probably offset the character itself just to make sure it's a little bit more aligned to the empty. Oops. Sorry. Let's I keep selecting the empty. I should probably stop. This doesn't matter as much cuz we can just offset it. But yeah, we don't have to apply location or anything. So, just repeat this process for all the other characters. And yeah, keep organized. It's showing this cuz it's in a different collection. So, let's just move it like there. And now it's highlighted again. Sweet.

**3:46:40** · And now you can see I moved all my characters into the center of 000. It doesn't really matter if there's just like a slight offset. You can always adjust for that in code. And then it's rotated towards the negative yaxis, which will be the positive Z-axis or towards us in 3GS.

**3:46:57** · Cool. So, the empties don't really matter, but they're just there for organization purposes. And if you want to like parent these to like the body as well, you can totally do that as well, but that doesn't really matter either.

**3:47:09** · Anyway, we're just going to Let's just right click, same thing as usual, select objects, and let's come over to file, export glTF. You know the drill. So, we want to replace our moving characters GB here with the one that we just exported.

**3:47:23** · So, it's going to be right here. And we can delete this one. Well, if you want to save a backup just in case, you can totally save a backup backup or whatever you want to call it. Now, all we have to do is process our models with a script, but I don't want to run it for all the other ones again. We shouldn't need to change anything there, unless some of those are moving. I'm just going to move them into scripts folder temporarily as I rerun my script. We want to create another folder called process assets.

**3:47:50** · You can totally do that, but whatever.

**3:47:52** · I'm just going to move it there. And now we can just run our same package.json file. So, how handy is that? We just run the same thing, right? MPM run gen models. And I know I did make some fixes to it. So, hopefully it outputs in the right place now. And you did. And indeed, it did actually put it in the right place this time, but it just overrid our other file, which is not what I want. So, I'm going to undo that and I'm going to Ctrl + Crl +V to copy this.

**3:48:22** · So, I get an old one and let's just up arrow and rerun that again. So, it doesn't overwrite. And sweet. So, we still have our old one here and it just overwrite our other one thankfully. And it looks like I didn't fix this part yet, which is fine. And then this one, I didn't fix that one either. So, let's just come over real quick to KTX loader.

**3:48:44** · If you're from the future, you probably will see this fixed, but whatever. Uh, it's really just naming convention stuff. And yes, I know it says use K2X2 texture, but this also handles webp textures. So yeah, just ignore that. I'm going to update that. And by the way, you the React 3 fiber Dre hook might be working by the time you watch this video. Or if you're not using the web GPU renderer, then it would work anyway.

**3:49:07** · Sweet. So, let's just open our copy side by side and just copy everything that we have over here into the new one. So, that's all I need over here. I'm actually going to put it underneath the texture just like so. And just make sure to import everything. Use progress store, use frame, use ref. Cool, cool, cool. And we can even copy our griier.

**3:49:27** · So, I'm going to I'm going to copy this right over here. Alt and highlight that.

**3:49:32** · Ctrl + C. And then let's see. winter arm front and winter front character like so.

**3:49:40** · Cool. And then oh actually let's alt down arrow. Oh this time it's in order.

**3:49:44** · How convenient. I'm going to control x that winter head front.

**3:49:49** · Yeah. Okay. So let's see. Winter head front.

**3:49:53** · And let me just make sure that's it. I remember we last time I had a duplicate.

**3:49:57** · I might have I think I might have accidentally named it duplicate.

**3:50:01** · Moving characters winter score. Okay.

**3:50:03** · You know what? It doesn't really matter cuz we'll just fix it when we need to fix it. If I go back and refresh the page. Come on. Please work. Oh my gosh.

**3:50:10** · It worked. Oh my gosh. It's too easy, guys. It's too easy. Oh my god. Bring me a real challenge. Like just Come on, guys. It's just too easy. It's just too easy. Anyway, now you can see it's rotating along as we're moving to the curve. It's actually not rotating. It's actually pointing in the same direction every single time. It's our camera that's rotating that makes it look like it's rotating, but it's actually not rotating at all. All right. So, how do we fix that? Well, as we mentioned before, we want to use a cross productduct. And this is how we get a perpendicular vector to two different vectors.

### Basic cross product formula for rotation orientation along curve

**3:50:39** · So, as long as we can get two different vectors like an up vector and a directional vector, then it'll just point inwards. If you can imagine this guy's hand is like the circle, then all we need is just two vectors. So, how do we get two vectors? Well, the up one is obvious. We just create one that points up ourself. And how do we get this other one? Well, the good news is there's actually another thing that's called the tangent, and it pretty much just shows you the direction that you're going in.

**3:51:05** · So, if you remember from like geometry class, I don't know, maybe in like middle school or something, you calculate tangents and stuff like that.

**3:51:11** · That's the other vector that we're going to be using. And there's a method built in directly called get tangent at. So, we don't if you want, you can check that out in the documentation, but we don't even have to do any hard work or mathematical formulas. Let's just shift alt down arrow. Let's call this whoa shisa tangent like so. And there's this thing here called get tangent tangent just like so. And we're just getting at the scroll progress. Now we need an up vector. So let's create that. I'm going to go into custom camera real quick. And I'm just going to copy and paste that.

**3:51:41** · You don't have to highlight the line by the way to copy and paste it. This is like a force of habit. But you can just control C on the line and it'll paste it for you yourself. And then let's just copy this target look at in over here as well because I'm too lazy to type it out. Let's make sure do control spacebar to import. Use wrap. Sweet. And let's just shift all down arrow and create another one. And this is going to be our f vector. So we'll just do up vector. So target look at is our results and perpendicular one. Right? The product of the cross productduct of a and c that gives us b.

**3:52:11** · And we're going to be looking at this instead. Now we can just take the target look at over here.

**3:52:17** · Target look at current. And the other built-in function that you can find on the 3GS docs is cross vectors. And of course, we want to cross the tangent of vector.curren up of vector.curren. And and by default, this will just shove it directly into this right here. So it looks kind of funky, but you'll get used to it. Now, we should just be able to copy this and instead of position, we just want look at and like so. And then we should just be able to pass in target look at over here. And let's just make sure we spell tangent right. tangent right over here.

**3:52:48** · Let's just make sure this is current as well. And voila, take a look. It's working. Okay, now we all we have to do is just create a bunch of group refs and wrap our other ones manually. So, could you automate this in the script? Technically, you probably could if you have the right naming convention. I don't know. It's kind of a niche thing to script. I don't know, unless you have like the same kind of workflow, but we're just going to manually do it this time. And I'm just going to wrap all my stuff with refs. So you can totally do that as well if you have more than one object or you can just skip ahead in the video. Sick.

**3:53:19** · So I have all my references here and they're just wrapping stuff over here. Order does not matter by the way for this JSX stuff. But anyway, now we just need to extrapolate this to an old function cuz we don't want to type the same thing multiple times. And we need to give each of them an offset. So let's come over here and let's start with const offsets.

**3:53:40** · And I am too lazy. So, let's just alt doubleclick all these lines over here like so. And then Ctrl +V to paste those. And let's just make sure to select all these with different cursors.

**3:53:52** · Again, I'm just holding alt and I'm just going to set zero at the moment and comma just for some offsets. And then we can arbitrarily set some. We will find these later. But now we'll just create a usable function. So I'm going to call it move. And we need to pass in the ref because we have a bunch of refs, right?

**3:54:09** · So, we need to get the ref and we also need the offset, which is going to be coming from over here. So, we'll just do offset. Sick. So, we should just be able to copy this whole thing over into Let me just make sure. Yeah, let's just take all that and put it in here. And instead of this, we'll just do control D control D. Replace that with ref. And that'll check the ref that we pass in over here.

**3:54:32** · We can just do plus offset. And then we'll just do plus offset over here.

**3:54:37** · plus offset. And now let's just copy this function over in here. And we're going to pass in our refs. So let's make sure let's make sure we have it seven times. And let's hold alt and double click all these. So we create seven cursors. Then come over here, crl alt down arrow to quickly make some cursors.

**3:54:55** · Crl +v to spacebar that. And then we'll do offsets and then dots. The same exact thing writing again. So yeah, now we're just calling that. Go back. Everything is disappeared. But we can't see anything. And if we scroll too far, we're going to get a crash because we're going past one. So that's what that's showing. There's no value past one on the on the curve. So maybe like 0.5. And even that is like way too far from where I want to start. Actually, I think I want this to start directly on top basically or virtually basically.

### Character moving fixes, updates, and looping

**3:55:25** · So I'm going to make it like this. And this is probably like 0.14 I guess cuz Yeah. And I got it. Wow. And I'm not going to pretend like I know what summary offset is yet. So, I'm not going to touch it. Let's fix up our progress scrolling so we don't get the glitch first. Okay. So, now we want some progress ranges. I feel like I feel like we could put all the used refs in an object with this as well as the progress ranges of where we want them to move.

**3:55:59** · Um, but I'm just I don't feel I'm not in the mood of reorganizing the code into a single object. So, I'm just going to create another one, and we'll just call it winter. We'll give winter a start of zero and an end of well, spring started at 0.14. So, I'm going to start at like end at 0.2. And then we have let's see what else. What's to next? And I'm just going to arbitrarily set values. I don't know if they're right or not. 0.48 and 0.60.

**3:56:29** · It doesn't particularly make sense because each one should be at uh oh that's because I start with an offset. Never mind. It doesn't really matter. Anyway, we can fix that later.

**3:56:41** · And I'll just call this progress. We need to update our move object or character to take those in like here.

**3:56:47** · Actually, we could split it up from here if we wanted to. We have a lot of options here. I'm just going to get rid of Sorry, I'm going to rename this to range because I don't know why I just copy and pasted that name there. Sick.

**3:57:01** · So now we can just pass in all this stuff. And I'm just going to come over here and like so. Just like so. We just pass in the progress move ranges. And now we can just uh deconstruct from this itself. We'll just deconstruct here.

**3:57:17** · We'll do const start and we'll get it from the range object that we passed in over here. By the way, if this looks messy where we're calling a bunch of stuff in this function, you would be right. But there's no point of refactoring this cuz we're never going to come back here and attach another character or something. If you need to make it scalable, I would refactor this code. But for us, it doesn't really matter. Okay. So, instead of just remapping, I'm actually just going to also add the lurping step as well for the characters cuz right now again, we're just getting the point on the curve. So, it's a little bit jaggedy.

**3:57:48** · You can't really tell because it's a continuous circular curve or like mildly distorted. But when you're on like mobile devices and I go control shift I, you can see what happens when I do a little bit of a tick. You can see it kind of feels like it's ticking along the curve. So, we need to also add our own custom looping here. Just the same exact way we did with our custom camera.

**3:58:11** · I know there's another issue, but we'll resolve that as well. It's the issue where when you tap, it's actually updating the camera rotation as well when you just want to swipe. So that's something we'll fix in the responsive section. So the first thing we need then is to check if we're in this range. So if scroll progress is greater than end and start, that means we are good to go.

**3:58:35** · If you want to use a guard clause instead, yeah, we could do that. So we can do or and then just flip these. If it's less than end or if it's greater than start, we just return and we don't run anything below. So, next thing we want to do is calculate the progress between the start and end values. So, we go from like let's say we're halfway in between. We want to have a value saying we're 50% of the way in between 0.68 and 0.48 and so on so forth for all these other values. How do we do that? Well, let's do const and we'll do progress.

**3:59:07** · And the formula, you've probably used it before actually. It's just your current input value minus your starting value divided by your ending value minus your starting value. Okay, now we can just do const and we can do points. It'll be our range progress, right? Which is a value between 0 and 100% times our ending minus our starting value. Okay. And yeah, let's just get rid of this at the temporary moment. So if you don't understand this, let's say scroll progress is at 0.06.

**3:59:38** · Then 0.06 06 minus the start is just 0.06 and then we're dividing by 0.112 which we get 50%. So range of progress becomes 50%.5 \*2 minus 0 is just going to be 06. So the point that we want to get 50% of the way in between this is 06 and you can do this calculation for any range and you will get uh your expected result there.

**4:00:06** · So now we should just be able to do point over here like so. And sorry I shouldn't let me undo that. I shouldn't have gotten rid of this over here. So point let's rename this instead of point and add point uh maybe curve value. I don't know curve value would be better.

**4:00:24** · I don't know. And let's just place that in here instead. Like so. Just like so.

**4:00:29** · And sorry I am wrong. If the scroll progress is greater than the end value or if it is or if it is less than the start value, we don't want to do anything. Sorry, my bad. And now if I refresh the page, let's see. Okay, we got something. We got it working and it works.

**4:00:50** · And yeah, I don't see the other ones because of their ranges and stuff like that. So I think what we can temporarily do is fix up the offsets and ranges. So what we can do then is just come over here and console.log our scroll progress. That way we can just see actually we could just put this in our use frame. Why not? Yeah, just over here. And what I'm going to do is just scroll around and kind of just arbitrarily guess at what scroll progress value.

**4:01:19** · So I'd probably end this around like 0.65 0.61 six one or something. I'd probably start this one at like 0.31 and kind of just do that and we can always fix that later. So here you can see that I updated my offsets and progress move ranges. I'll I'll adjust this later as well. So when I refresh the page, you can see that it starts right there as soon as I start scrolling. Same with the next character and next character and the next character. Now there is an issue here.

**4:01:51** · You can see when I go into a loop, it's going to teleport back at the start.

**4:01:54** · Same thing here. It's going to teleport at the start cuz it's right right now.

**4:01:58** · It's like over into oblivion. And then as soon as it goes here, you can see it just teleported from the right to the left. And this should happen on the way back as well. If the characters start Yeah, as you can see, if it starts on the left, it's going to teleport to the right. Now, in Mr. Panda's video, this is exactly what I did not bother solving in my loop. You can see when I go over here and into the next uh the next loop, I come back down and it teleports all the way back.

**4:02:26** · Now, the reason ours is jumping and the one here is not jumping is because I added linear interpolation.

**4:02:33** · So, it actually linearly interpolated back to the start rather than to the front. So, this is actually the same exact behavior. We just haven't added linear interpolation yet. So, let's add linear interpolation and then let's deal with these offset issues in a little bit. And I'll show you another way to make it a little bit more smooth so it doesn't like teleport at the start. I feel like you already know how to do this, but I'm going to do it anyway. But feel free to skip ahead. Of course, we need a target position, right? So, we come over here. Let's add that target position just like so. And we want to linearly interpolate that instead.

**4:03:05** · So, let's place it in here. We're going to do target position. We don't need this variable no more. Ain't nobody need that variable no more. Right. Right. All right. And we get rid of that. Let's just make sure. And instead of ref.curren, we want target.position.

**4:03:25** · Uh, sorry, this should be current. And then target position.curren.

**4:03:29** · Target position.curren. And then we should just ref.curren.position.lurp.

**4:03:33** · And we want to go to the target position.curren like so. And then we don't need point here either. And now if I refresh the page, you can see that well they're lurping there to the offset first. But as you can see, it's it's essentially the same thing. We just need to fix that issue. It's the same exact behavior as the panda one now. So the first issue I want to solve is always make it go to the end or always make it go to the start.

**4:03:57** · Once I'm past the end, sometimes if you scroll really fast, it won't go to the end value because we'll be outside of it and this no longer does is no longer triggering or doing anything. So, I want to make it go all the way to the end or all the way to the start every single time, which is something I did not solve in the Panda one because I just wanted to move on, but we'll solve it right now. As I said earlier, it's a very simple fix. We just need a clamp to the starter end values.

**4:04:21** · So, I'll just call this clamp progress and you just take the math or maximum value of two things. In this case, it's either going to be the scroll progress that determines that or it's going to be our starting value. So if our scroll progress sorry I keep saying starting but the variable name is start. So basically if scroll progress is greater than the start value then just use the scroll progress value otherwise use the starting value and then the same thing with the end value. So we'll just do the same thing except it'll be the min.

**4:04:48** · So here we change this to min and we want to pass in the end value here instead. So let's don't forget this.

**4:04:59** · And instead of scroll progress we want to use the clam progress over here just like so. No longer need this. So, we can just get rid of the guard class. So, now when I refresh the page, let's take a look. Everything lurps there, which is fine. We'll fix that as well. But when I go here, it's going to work perfectly fine.

**4:05:17** · And then once I get to the end, it's going to teleport to the start. It should. Yeah. And then all of them start at the start again. So, in the Panda video, this one would have been ideal because everything resets rather than we have to it teleports at the start. And the same thing should go on the back way. So once I hit this, everything should teleport backwards. Yeah. Okay, great. It does that. So the next issue I want to do is that it loops to that initial position.

**4:05:44** · Now, we don't actually have to fix this because we have a loading screen, but it's better just to fix it. So I'm pretty sure you probably already know how to do that, so feel free to skip ahead. But for the people that want to know how to do it, it's just basically a use effect, right? When the component mounts, use effect. It's just going to run a single time the first time that we're in. And we just need an empty dependency right here because it's just going to run on there.

**4:06:10** · Technically, I guess we could wait for curves, but it should be fine either way just to leave it empty cuz curves will be initiated anyway. Anyway, we can just create a map of refs and objects. And then we just loop through them and get the point at each offset and set our ref current position to that point. I'm not going to waste your time showing you that. So here you can see my map is just winterfront character offsets. And then for each item in our map going to get our ref and our offset. And then let's just come over here and copy this because I'm too lazy. And we should just be offset over here.

**4:06:42** · And then we can actually use the lur vector here. But instead of lurping towards that, we're going to go back to what we did before.

**4:06:50** · We're not going to use lurp. We're just going to do ref the ref that we have the current value of that and the position.

**4:06:56** · And we're just going to copy it instead of loop to our target position. And we can just get rid of this. So that's all we need to do. And once this is mounted, should only run once because we're never rebuilding the curves. So now when I refresh the page, you can see nothing is lurping there. It's just copying directly there on on refresh. Again, that's an optional change, but whatever.

**4:07:14** · Okay. The next thing I want to do is use GSAP to animate the stick going in and out, like up and down while we hit the end and start ranges. So the first thing I'm going to do is put an inner wrapper for all the single ones. That way we don't have any conflicts because if we animate this with gab up and down, we're doing the lurping to the position. So it's going to keep getting overrid with our gab animation. We might see like blips of animation or whatnot, but it'll just keep conflicting.

### Animating characters popping in and out with GSAP

**4:07:44** · So, the easiest way, well, we could do like flag variables and whatnot, but that's just a lot more messy than just having another inside wrapper for all these single ones. So, that'll be like winter uh front character character inner wrapper.

**4:08:02** · Whoops. Inner wrapper like this. And we're just going to have every single one have an inner one as well. I'm going to shift up arrow just like that. So, I'm going to do that. And we're going to animate this one inside the gap. And then this one is going to be the one lurping. Okay. So, let's just shift alt down arrow this. It's getting a little messy. Maybe we should have created an object, but it doesn't really matter. I'm just going to select this.

**4:08:24** · Ctrl + D. And I'm just going to right and then inner wrapper. Wave inner wrapper as well. And now we have all our inner wrappers to use. You know the drill. Just copy all of these. And now I'm just going to control D and select all the offsets. The next F. Then I'm going to go to the end of the line and I'm just going to go back over here, hit enter and space bar uh sorry enter and then just paste over there. And now we can pass in our inner ref here as well.

**4:08:54** · Interf and now we can reference that.

**4:08:56** · Let's see what we need is just to check if scroll progress if it's greater than start or equal to it then we just want to play a gab animation. So gub two and it'll be inner ref. ref dot

**4:09:12** · oh sorry notref doc current we can do like let's just do y equals like two or something something that goes a little bit higher so it's noticeable and let's set a duration I think default is 0.5 but I'm going to set it there anyway and we can just try this for now so as I scroll and it enters it plays the animation which is exactly what is expected over here just like so and then it stays stuck so now we just need to do the opposite it.

**4:09:38** · So if scroll progress is greater than or equal to end, it means we cross a threshold and we want to make it go outside of the world. So it should be this one should be neg five, right? Or whatever maybe like I don't I don't know what value I'm going to put here, but neg five. If I refresh the page, okay, plays intro, that's expected. This plays and then that plays. And that should work for this one as well. Okay, cool. And now we just need to go the backwards, right?

**4:10:09** · So this one looks a little funky because again the starting point is here. So there's no range here. We're going to fix that right after. So now we just need if it's less than start, we're going to do if it's less than start, what what what are we going to do? We're going to if it's less than start, we should make it go down again. So we can just copy this over here and just paste it like so. If I play, it should go back and forth just like so. Same thing here. where it goes back and forth.

**4:10:37** · It's feels a little bit off because the syncs the starting and ending values aren't perfectly synced. I didn't bother fixing that yet. Now, what we need to do is make sure to set all our positions at the start over here.

**4:10:50** · And we just come over here, position an array, and we'll just do like uh I don't know five or whatever. I I don't know.

**4:10:57** · So, we can just do it for each one. We could also set this in our use effect above, but we might as well just manually set it. Sweet. So, if I start back and refresh, that plays. Everything has disappeared. That plays. I don't see the other character. It's probably because I I've flipped normals, but it's fine. I'll resolve that off camera. And now I'm just going to change these to arbitrary values. If you want to play around with the easing and everything as well. If you want to use a timeline, you can totally work with the timeline as well. So, maybe like 0.2, something slightly higher than zero.

**4:11:26** · And these are I'm going just going to make it consistent with our other one. Okay.

**4:11:32** · Now, we need to fix the winter bug where I start in the center. Uh, I think while you could do math to make it work, it's probably just easier just to start at the other point instead of this point.

**4:11:44** · That means we're probably going to have to update all our progress values, which kind of sucks, but hey, whatever. Yeah.

**4:11:49** · So, I'm going to start with this one over here. And yeah, so I'm just going to use that one. And we can just look for0.035.

**4:11:59** · If you want to adjust and reexport your curve, you can totally do that. We should just be able to play with some offsets. So now we can just look at 0.193 actually and we can just copy that ourselves and we can look at the other one. So let's just go to curve and for our moving characters curve over here.

**4:12:16** · It's actually right over here. So we can just copy that right there. And then our starting index. Oh, that actually just happens to be zero. So we don't really have to do anything. Okay. Now we need to fix up all the progress values. So let's do that. We might have to change the camera look at start target as well.

**4:12:32** · If you want to do that, you can do the camera look at curve and change the starting index at the moment. But um for now, I'm I have enough range just to adjust it in moving characters. And so we just need to adjust all this stuff.

**4:12:45** · The last issue I want to solve here is when it comes to looping, everything does work, but it lurps during the animation, but it's only an issue when we're looping cuz that is when it resets to the other side. So, it's actually not really that bad. All we have to do is check if we jump a large distance like from 0 to one or one to zero and we just create a flag variable basically that determines if we're looping or not.

**4:13:14** · So we can do that by keeping the track of the previous goal progress and then updating the new scroll progress and seeing those comparing those two values and determine if it's a jump or not. So let's create our uh our previous scroll progress previous scroll progress that will compare to the current scroll progress or our target basically use ref. And it doesn't really matter but I'm just going to set it to the current scroll progress. And now what we can do is come down over here and we can update our previous scroll progress right here.

**4:13:46** · So we'll just do previous scroll bar current equals our scroll progress. So we update it after we do this kind of stuff. And then inside here we can check if the delta or the difference between the previous and first one. So let's just create our calculation. So const difference in delta, but I'm just going to use English over here. Now that I think about it, I'm just going to do all of this in one line. And that way we just get a boolean. So it should be we can do like 0.5 or something. It could anything that's large enough. And I'll just call is a loop is a loop.

**4:14:16** · And then we can come down here and instead of lurping if is a loop then we just copy.

**4:14:26** · Instead of lurp we just do copy. And then we can get rid of 0.1 over here.

**4:14:31** · Now if I go back and play it you can see that indeed it does work. But because our GSAP animation is playing, it still teleports there while our GSAP animation is playing. Now, you might be asking, how come that only is an issue when I go this way? When shouldn't when I go this way? This this also glitches out just like that and teleports instantly. Well, the thing here is that I actually gave this one a 0.99 here rather than a one.

**4:14:58** · And then this one I started at zero. So, the cheekiest solution here is just to give it a slight little offset just like this. And this would work. But the issue with this now is that there's a time where there's no characters on the screen. And this is fine. This like this is completely fine if you don't really care that there's a time where there's no screen. If you want to do one and zero. Oh, sure.

**4:15:26** · I should probably give this the similar offset over here if you want to. It's it's a lot more work to do, but it's not that complicated.

**4:15:35** · Basically, the idea is either you store some user data inside the 3GS object itself and check for that or you give a key to every single character and each of them have their independent GAP timelines. So that way you check for a key and it doesn't really matter cuz right now we're sharing the grouping thing across every single thing like every single thing is being calculated at the same time. If you group things by keys then everything becomes a lot easier to manage in the long run.

**4:16:02** · And at that point if you want to go that route I would consider like uh you know putting every single thing together into a single object. So when I say single object, I just mean const and like um you know like winter main ref and your inner ref, inner ref. And then you have your offsets in here. And what else do you have? You have your progress move ranges. Progress move ranges.

**4:16:31** · Progress move ranges. And let's see what what else would you put in here? I think that would be like the main stuff. And then you just do that for spring, winter, and fall as well. That way it's just a lot more organized and you can use maps and other things just to go through it a lot easier, you know, whatever. It doesn't really matter that we're doing it this way. Also, sorry. I just realized when I was adjusting the camera that we should be using get state and in moving characters, I did this when I said that was not good. So, let's just get rid of this. And honestly, we don't have to do that.

**4:17:03** · You can put the get state in there as well if you want to, but we can just start that at zero.

**4:17:08** · It's not really a big deal. And then in our use frame, we can come over here and let's just name it scroll progress, which is what we called it here. I guess we should probably keep it consistent with what we named it there, but whatever. It doesn't really matter. And here, and now we have to pass it in to each one of these. Again, a little bit messy. I would consider refactoring, but we're home stretch already, so it's not really a big deal. And uh yeah, in our function over here, we can click to jump to that and just pass scroll progress there as well.

**4:17:38** · Hello, I am from the future. I just want to mention this now.

### Fixing infinite GSAP tween creation with IDs

**4:17:42** · I was planning to put it at the end and I honestly should have refactored it at the moment, but move object or character runs on every single frame, which means we create a tween on every single frame because it's always running on every single frame. Now, while that's probably fine for most modern computers, it is just not good practice to create a GSA tween every single time because these GSA.2 these are these are basically JavaScript objects. And if you want to check for that, you can console.log gap.global timeline.get children.length.

**4:18:12** · If you do it where you are in the video, you'll probably see it go up to like 700 and so on so forth. Then it'll go down to like 600 and then or like keep fluctuating back and forth, but ultimately go up. That's GSAP kind of trying to handle itself and garbage collect and so on so forth. Here you can see that now mine is a steady five and whenever it goes up it will clear out and stuff like that. I've added a lot of extra code since then but that is just something to keep in mind.

**4:18:39** · So use an ID and then you can also because we're sharing a lot of animations you can just use like a turninary operator to you know adjust the the way. So all I did was then just pass an ID because we only want to trigger it when we cross a threshold, not every single frame. So as long as we check if we cross the threshold, then we should be fine. So you could use that key method as well.

**4:19:02** · Then you would not really need an ID.

**4:19:04** · You could just use the the key that you give it instead. But I just decide to pass in ID because it was faster that way. Uh but yeah, if you ever questioning if you're creating infinite GSA timelines or whatever, you can actually just log it out. Okay, so there's a few ways to handle responsiveness and I'm just going to talk about like some of the more common ways. So, one of them is I just file saved incremental the curve one. I renamed each curve to mobile and I just adjusted them.

### Handling responsiveness

**4:19:32** · Quite honestly, I think the only major one that you do need to adjust though is mobile camera path curve. I don't think you have to adjust mobile moving characters or the look at one, but if you do, you can totally do that. Yeah. And the whole point is just file export again, right? And now you have three other curves that you can copy into your curves file. So I just reexported the mobile path camera curve and I just copy and pasted that into curve.js.

**4:19:56** · This is not going to be the final method I'm going to be using, but I just want to briefly talk about the next steps if you want to go the mobile camera path route. Okay, so I think the easiest thing to do is just put is mobile flag in here like is mobile and

**4:20:13** · just check if window.in inner width inner width for something I don't remember the actually we just add a window add event listener resize and every time we resize our window this is going to trigger and update the store over here and then wherever we need to use is mobile we can just get the state in here so we are going to be checking on every frame that's how we know if it's going to work or not and then instead of camera path curve over here curves camera path.curve curve.

**4:20:41** · What we can do is come over here and we can just make it const camera path curve and we'll just make a turninary operator. So if it is mobile we want to do curves domo camera path curve mobile camera path curve otherwise we want to do the regular camera path curve curve. We can just do camera.path curve over here. Now when I go back you can see that as soon as I get here I am now using the is mobile curve.

**4:21:09** · Of course, it's distorted because you have to go back to moving characters and also check for is mobile here. So, depending on your mobile curve, if it's close enough to your desktop curve and you just like move the points closer, you probably don't have to touch something like this. But if you have like more points or less points or something, you're going to also have to have like a ismo check over here and you know, just just deal with that as well because the progress might be different at different points.

**4:21:39** · And then of course you also need like is mobile checks for GSAP. Um well actually GAP wouldn't matter because we're just going up and down but depends what you do but yeah you'd need to float this up with a bunch of is mobile checks as well. Yeah. So that's just the way if you want to use a second secondary curve. Now the close the closest you make the mobile curve to the desktop curve the less work you have to do in moving characters. Anyway, since I'm here, I'm I think I might use it for another one.

**4:22:10** · So, I'm going to create a new one called use responsive store. Use responsive store.js.

**4:22:18** · Does it really matter? Honestly, no, it doesn't. Like, it's it's not really a big deal. Um, at all. Like, honestly, it might be a waste of space to create two stores, like one just for this one, but whatever. Just semantic purposes. And oh, I just realized I typed two different numbers here, which is fine. Okay, so now I just want to talk about some other cool stuff that you can do. And I don't I don't feel like I need to go step by step on a lot of them.

### (Optional) Analyzing AI LLM coding and tips

**4:22:48** · So I'm just going to rush through them. So the first thing here is the grass going up and down and some things rotating like the dragon over here. Now, these are very simple sign function animations. If you've ever seen the sign of x before, you can see that it starts at zero, goes to one, and oscillates back and forth. So if you use a sign value just like rotation or scale or something like that, it's just going to keep oscillating over time. So if you can imagine x is the time and then of course, right, you have offsets like you can add an offset so it shifts it.

**4:23:16** · You can add a multiplication so it changes the frequency and then of course you also have multiplying the whole thing which is the amplitude and how much it goes to and now it goes to four and neg4 and so on so forth. You could use cosine too but most people use sign for repetitive functions because it starts at zero whereas cosine starts at one.

**4:23:37** · There's a lot of other cases where you need to use cosine instead of sign but for animations like these it's typically using sign because it starts at zero. I know you could also shift this but whatever. One thing you'll see when you're analyzing someone's code, I feel like you should always be skeptical about what they're actually doing. If you look here, you can see I create like 11 refs and just like like this looks repetitive. And if it looks extremely repetitive, it's probably best not to do it that way.

**4:24:06** · Now, for readability and for like a beginner, this is probably the most clear way to understand what you're doing. For each grass blade, I'm creating a ref and then I'm scaling it with time and manually adjusting the the offset values. Like that is just verbosely clear, but it's also completely messy because I have refs for every single thing. The reason I did this approach is one because it's faster and you just let AI do all the generation for you. And two, I was never going to revisit this project.

**4:24:35** · So it's kind of just like more of a throwaway project if anything. So, when it comes to like looking at people's projects, even if they're cool, just like kind of be skeptical about what you're reading and what you're looking at. So, I do just want to follow up like when you're using like an LLM to help you figure out things and you like copy someone's code, which is what I did here. I copied this code. Is there a better way to do it? I gave it a pretty bad prompt. Um, more like just like a casual prompt here, like if I'm trying to learn something on my own, I copied moving characters and then also this file for myself.

**4:25:06** · And then I just gave it like a it's a pretty bad prompt. But like these solutions are good, but I as a developer I actually wasn't actually looking for any of these solutions. I was looking for more like a generic wrapper because if we do this for grass nodes in this file, then what about all the repetitive ones in other files? We would need maps in all of those as well, right? So I actually prompted it so to get what I want, which is a component that I can wrap them and that works out of across all the files.

**4:25:40** · Like I know it's possible, but I just put that anyway just because I like talking to the bot like a like a human I guess in in some way. And then now I figured out that that is possible and that it does exactly exist. I think one of the most important things like when I was learning coding was just like using things without actually understanding them. Like in React 3J or dry, there's this thing here called float and all you have to do is wrap your mesh in float.

**4:26:07** · So once you actually understand how this works, you can actually prompt the AI to do that that way instead of the other way that I was suggesting. In the past, I would just like copy this and not actually know what it was doing. Even when before LLM's like when I was reading documentation and now it's like you actually look at the code and you can see that oh hey, it's using like a use ref. It's wrapping it in a group.

**4:26:29** · it's doing something to like its position or whatnot. And you can see it has its own internal use frame here.

**4:26:34** · Again, that does not create a new request animation frame. It just goes to the internal one. So that's how float works. So I didn't even have to copy and paste this code into AI. It actually knows it probably because it trained on this honestly um because this is open source. But the whole idea is like once you actually like just dive into it, you can actually figure out so many other solutions that AI is not going to give you the first few times you prompt it.

**4:27:00** · Even if you don't understand what this is doing, you can copy this in instead and prompt the AI with it. So it's just like a small tip. When you look at someone's code and you prompt AI, it's not going to give you the most optimal solution for what you're looking for every single time. So just be aware of that. The great thing about documentation is they usually have a link to their source code. if it's open source, which is so amazing. Shout out to Cody Jason Bennett for this. So, just a few other notes, random notes. When you're using this component, make sure you pass in the position if you want to use the local axes instead of the group.

**4:27:30** · When you're just going up and down like this over here, I did not bother passing in the position nodes into the function over here. But for the deer head, I wanted to use it local axes. So, I passed that in into animate mesh. Try the local axes and repositioning your group and it still doesn't work. You might have to go into Blender and apply rotation and scale or adjust your origin point again. You shouldn't need to apply location because that'll just reset the origin point. But those are some of the other things I would try as well. Okay, so just some things to talk about.

### (Optional) Cool idea - zoom slider

**4:27:59** · I just quickly added some vibe coded in code stuff, but just to show you like uh some things that I was thinking about adding that you could possibly also add if you're going for a paper craft portfolio. I'm going to come back to polish up this code. So one of them is having like a ro like a zoom slider. So as you zoom it's going to change the camera zoom.

**4:28:21** · So the way I did that was I just created a zoom slider here that was just basically an HTML input and then updated a use camera store the store value over here that triggers in our and that triggers in our custom camera over here. You can also see I got rid of the tapping thing the offset on mobile devices. So I just checked in our responsive store if it is mobile then don't offset it at all. This one I did give a slight offset on the X direction because I wanted to move the camera slightly left. It's like a cheeky way of adding another sort of offset to the camera that but originally it would just be zero.

### Fixing tapping camera offset on mobile/touch devices

**4:28:53** · As you can see, I also added an intro screen. Again, it's still buggy. I need to like preload images correctly and things like that. But one thing I just want to say about the intro screen is that the use progress goes for every single asset. So, it goes to 100% and then goes back to 0% and 100% for every single asset that you do. So in scene, you can see that for each one of these that it loads, it's going to go to 100% and then back. So you probably seen in my other videos where I just use progress and it goes back back and forth.

### (Optional) Note on useProgress with React Three Drei

**4:29:24** · Here you can see when I refresh the page, it's going back and forth back and forth, right? So that is an issue that you have to resolve. Again, I just vibe coded the solution for that. I need to go back and clean that up. Some cool things you can do is like have the character also ride the bar. So, this is inspired by a friend that I was working on with a different project and she made the character ride the bar over here and you can give her a follow. She's also credited on the website.

### (Optional) UI inspiration design

**4:29:48** · Another cool thing you can do is like have like a info button over here and it just shows a little bit of information like the canvas button would like hide and stuff like that. Again, there's responsive issues and things like that. Of course, I just added the animate mesh thing to a multitude of objects. That's why you see same with the moving characters as well.

### (Optional) Cool idea - make canvas smaller

**4:30:07** · So, if I come over here and look at animate mesh, you can see that it's wrapping everything inside of that original group. You can see I have another group here, and that's just for the idol. When I scroll, you can see when I scroll, it switches to the other character, and so on so forth, just like so. I just wait 3 seconds and it'll swap to the idol character. Now, I got rid of the text box and the intro.

### (Optional) Cool idea - make an idle character

**4:30:30** · I was I was going to plan to make an intro, but I felt like it would just be better just to get straight into the straight into the experience rather than have an intro. But maybe I'll go back and add an intro later. One thing I will say about animate mesh though is again I updated it so you can pass in multitude of different properties. So you don't just limited to rotation, scale. You can do both rotation and scale if you wanted to and so on so forth. Another super simple thing is when you hover stuff, it shows up.

**4:31:00** · Now, I just realized the terrible usability there. You could probably also create like models and stuff like that, but I did cover that in a previous video, so I didn't really want to do it again. Oh, one thing I do want to mention is wrapping in suspense. Now, I think by default, Reactor Fiber does have suspense already built in, so you don't actually have to use one, but you can also put your loading screen part here and pass in your loading screen over here if you wanted to as well. So, you have uh more more than one option there if you and then app.jsx JSX.

**4:31:28** · This is why for main.jsx, it's just the app, right? Because sometimes you want to put stuff in the app level. So, this is just my responsive one when I go into open info button. I would I would probably refactor this a little bit if I was like actually coding it. Again, this was just vibe coded stuff, but it's just like ideas that you can do for your future projects.

### (Optional) Miscellaneous Random cool ideas to add

**4:31:52** · Um, yeah. And I was like thinking about like adding music with HowerJJS, which I covered before, or like clicking this and it would like play a little animation or like little paper craft animations with shape keys. Like they would build up little paper trails as I walk. When it comes with TSL, I was thinking about just adding little bit blotches of color along like the ways over here. So the paper would be like changing color in like real time and things like that. And of course, shout out to my patreons for supporting the channel.

### (Optional) Shoutouts!!

**4:32:20** · I know it's kind of unethical to ask for money because I barely post, but like uh it really does mean a lot.

**4:32:27** · Like YouTube is just not financially sustainable. I'd love for it to be, but like at the same time, it's just like kind of a hobby at the moment, and I'm kind of happy with the way that it is.

**4:32:37** · There's nothing on my Patreon that you won't get if you just ask me or you check out my YouTube channel. But maybe one day I'll do something about that.

**4:32:44** · But shout out to all of you guys. Uh you know, thanks. You don't really have to do that, but it really means a lot to me. But yeah, that's pretty much it.

### (Optional) Rambling, TAKE CARE AND PEACE OUT!!!

**4:32:51** · Thanks so much for watching. I hope you enjoyed that video or sorry, this video.

**4:32:56** · And make sure to subscribe if you want to. You don't have to. I just, you know, YouTubers, they ask you to do stuff like, you know, whatever. Anyway, take care. Thanks so much for watching and I hope to see you in my next video. Peace out. Take care. Bye.