![](https://www.youtube.com/watch?v=zyWD2E8AHCg)

## Transcript

### Intoduction & Project Demo

**0:00** · Hello, welcome back to another tutorial video. So, I'm just going to scroll slowly and as I scroll through it, I'll just talk about what this video is about. So, I did make a longer video.

**0:10** · So, if you watch that, you probably don't need this one. But I do talk a little bit about some project specific details towards this one that I don't cover in that video. But if you watch that other video, you probably don't need this one. This is more of just for the more advanced people or the people that just want to like compare and contrast ideas. So, it's a very simple portfolio. It's just a notebook and some image textures throughout the whole thing, which I'll show in a little bit.

**0:36** · And then I'll just talk about some of the key takeaways that I learned from this project. And yes, it does infinite loop. So, you can go back and forth as many times as you want. Also, when I put award-winning in my titles, it's not that I do these for an award. It's because I want to show you that you can actually win an award with pretty fairly simple websites compared to some of the other crazy things you see on the wood shop.

### Notes on awards, you can win too!!!!

**0:57** · Like every I think every single thing that is on this channel so far is relatively simple when it comes down to technical knowledge of coding wise and yet they still win awards because it's more of just like the emotional storytelling that you give rather than technical complexity. So my whole point is like you can win one too. That's why I submit to wards just to show you that you can win as well. Now, what I actually want to mention is an article I wrote on code drops that is associated with this experience and it's a lot more important than the ward or the experience itself.

### Notes on Codrops article on Workplace abuse, you're not alone!! Reach out anytime!

**1:28** · It's about abuse and like kind of where I feel like the industry is heading at least in this current state and how it's going to get better over time. As someone that was abused, not just by family members, but also by workplaces, I decided to write it in order to help possibly protect some people. So, if you feel alone, if you are abused, feel free to reach out as well if you need someone to talk to.

### Setup Image Textures in Krita and Bulk exporting

**1:54** · Okay, so the first thing I did was use Critter, but there's so many other options like Affinity and Procreate, whatever you want to use, Photoshop. You could even do it in Blender if you want to, but I used Critter to draw some stuff. Everything that I wanted to like move or select was on a separate layer.

**2:10** · That way I could just export it as a separate image texture to use into Blender. And then I just come over here to tools scripts and it should be export layers over here. And then you just select the one that you want. So actual panda here. Navigate to your location.

**2:25** · And I'm changing it to PNG so it sports transparency. And I'm leaving adjust export size to layer content off. That way everything shares the same canvas size, which I kept 3000 by 3000, which is kind of overkill, but yeah. And you'll see why in a little bit. So if I go back into Blender, I'll just show you what it is. It's literally just a bunch of planes with image textures. Let me go into render view and just show you that.

### Blender Overview

**2:48** · That is literally all it is, including the writings themselves. I wrote those as image textures and I just put them on a plane like so. Now, the reason I had all images used the same canvas size, well, not all of them, but most of them, especially the ones that I'm going to replace, is because that way I don't have to update the UV, and it kind of just looks like an overlap. So, this is moving panda, and I just switch to a different outfit like Samurai at Pond, Samurai at Panda, or like pirate panda or something like that.

### Why I kept the canvas image size the same size

**3:15** · You can see it doesn't move, so I don't really have to make any UV adjustments or any manual adjustments in code. Now, what I did in the project was inefficient. I had four different planes and I just baked them all separately. Oh, sorry. Yeah, obviously duplicate the material and whatnot. Yeah. So, I had like I think I had each of these on one separate plane and then I just baked them and I used four different textures to switch between. I know it would just be easier just to make like a spreadsheet of all four of them and then just offset the UV a constant amount.

### You should use a spritesheet, not what I did XD

**3:45** · That way I don't have to manage four different textures. I did not do it that way because it would have taken an extra like 10 minutes. So, I just decided just to put them all on four different planes and then have them swap in in code. I think as a anyone that is working on a project, it's more important to have fun than always optimizing everything. As long as you know what to do for a quote unquote real project, you should be good to go. Now, everything that was moving, I separated out because, you know, when you like bake things over each other, it's going to have a shadow.

### More Blender preparation

**4:15** · So, if I put the bike wheel on top over here or even behind, either the bike is going to get a static shadow or the wheel is going to get a static black shadow there and they'll show as I rotate. So, that's why I kept everything separate. And then once I was done baking, I placed everything back into the scene where I wanted them to be. So, as you can see, I just baked everything according to their section. I didn't bother separating and optimizing much at all. Like, I could just bake one of these, right, and instant them.

**4:42** · I just literally just use multiple planes and just bake them on a single texture just to save time. Okay. Now, for each section except the first one, I had one 4K texture. So, for the ocean one, I had one. This one had one. And then the this one also had one. Now, it looks a little bit awkwardly offset. I could have fixed that, but I didn't because I was just I just wanted to move on. So, I didn't bother aligning stuff and and whatnot.

**5:09** · So, that's why it looks a little bit funky that I'm baking this here. I did have some texture painting on the ground. That's why you see the color in the portfolio. I no longer have access to that image cuz I deleted it. But I just use texture painting to paint like the grass and the water and everything like that as well. Yeah. And I just use multiply to mix the image or the texture paint with the paper one by itself. So if I just get rid of that, you can see that's just the default image texture.

**5:35** · And then I just mix it with my own drawing one. And then I used the alpha channel to cut it out. Basically, you can see that this is the baked setup.

**5:44** · Sorry, let me just go. I don't have the images anymore. But after I baked them, I just organized them like so. You can see that I just placed everything back where I needed them. I do want to mention that each moving object, it was baked on its own texture. So, the camel, the ship, all those shared the same texture. You could totally put each scene's moving character as part of its own texture. like the bicycle as part of first scene texture and that's like totally perfectly valid as well. Yeah.

**6:12** · So if I go back to the code here you can see that each one of these was a GB file. So if I come over here come to models you can see each of those was a GB file and I just loaded texture and I just used it. So here you can see panda I load each separate texture instead of one sprite sheet. Again this is bad but it was a lot faster to do than use making a spreadsheet. Okay, I actually want to cover some stuff that I did in the other project that I should have done for this project. And one of them was have a naming convention.

### AI generated custom Node.js script for creating models (repeat from other video)

**6:41** · That way I could just write a script to automatically populate the textures rather than manually doing it myself. So I actually wrote a Blender script. Well, sorry, I used AI to generate a Blender script that would take like the first format over here and just attach it to each mesh name in the bake. This allowed me to write an easy script to detect which texture I should be using just based on the naming convention.

**7:06** · So if I come into my package.json, you can see that over here I have this custom script here called gen models and I used AI to generate this script over here. Basically what it'll do is like use the file name itself to replace texture names. You can see all my textures also have the same naming convention. So that really helps when it's like using re regex strings. Is that what they call them? Uh rejects reject strings to easily replace stuff.

**7:36** · So basically the idea is I place any object that I want in raw assets. So it'll do multiple at the same time. I just have one there. And I'll just mm run gen models. Gen models. And actually let me copy this one first just so I don't overwrite it. And it will output the new scene right over here. And you can see it has a lot of default settings related to the project. Here I imported my custom texture loader. It path to my texture public folder for me. It finds all those relative ones again based on the scene name here.

**8:06** · And then it also detects that based on my geometry also using the same ID here. And you can see this last index here is hooking up to the texture associated with it. There's a lot of other changes. For example, it adds the /models for both of the file paths here. So I don't have to waste time doing that. And then by default, MPX GLTFJSX does not have default here.

**8:30** · So it also automatically adds default as well. So let me just show you what that would look like if I use the command line tool or this online tool here. You can see no defaults, no hooked up textures. And it uses a hardcore position here. And it also has cast shadow and receive shadow. Again, this was fully written by AI. And here you can just see the NPX, GLTF, GSX script, though. Okay.

**8:49** · So, when it comes to the camera movement, basically all I did was I made two curves and then I used that custom Blender add-on that you can find in the description that I wrote with AI just to export it as a JavaScript file of control points. So, they both adjust camel ROM curves over here. You can see this one is for the camera and then this and this one is used for the panda. Now, I do want to talk about the brief looping. So, when it comes to the looping, there's a lot of ways to handle this. I did a pretty weird way.

### Camera curves in Blender and shifting & looping logic

**9:20** · Basically, what I did was I shifted all the points over here every time we reached a threshold and it would initiate a transition curve like something like this. It'll enter a transition curve and then it'll hop off the transition curve and go to the next set of points. Now, I did it that way because I felt like it was easier to do it that way. The other common way is like every every time you hit like a point, it will just shift the next point and then you hit this point and then it'll shift the next point. Now, I felt like this was a little bit more math heavy because all my rotation logic was based on the scroll progress value.

**9:52** · And every time you shift a point, it's going to change that 0 to one range of the curve. And I didn't want to deal with that. So, here you can see in my curve file, I have two curves. I have the camera curve and I have the panda curve.

**10:07** · My moving objects for this one, unlike the other one, not path on the curve. I just made it go left and right basically. And in my hook over here, you can see I've used scroll curve. So basically you can see what it does. It takes the last point of the first curve as a starting position and it takes the first point of the shifted curve as its ending point. So that is basically the transition curve itself. And then here is where I just shift the curve points.

**10:31** · Now, one issue I had with the transition curve is because it's only between two points and it still has the value between zero and one, the scrolling was extremely slow when I was on that transition curve because I'm not going much of a distance, but I'm still scrolling the full way. Whereas, when I get onto the main curve over here, you can see that because the points are there's so many points, the same scroll that I do on a tick is going to travel a lot farther than on the transition curve.

**11:00** · Now I solved this issue by having a scroll speed multiplier and if I was on the transition curve I would multiply it by six. Now this is bad because what would happen is as you can see as I enter the transition curve and exit it there's like some sort of force here.

**11:16** · Now the reasons for that is because basically if you leave it at six your scroll progress is going to jump up really fast. So when you enter the new shifted curve, it's going to like teleport or jump a really really far distance because your scroll progress would be like 0.3 and it'll just like jump to 0.3 progress on your on your next scroll. So what I did to manage that was even cheekier right before the end of the curve change it back to one.

**11:44** · But even then if you scroll too fast you can see that it's just going to jump a little bit. So it only works when you scroll smoothly and it that's fine as well. So, what I should have done instead was actually a lot easier. And I don't know why I didn't think of it, but I should have just multiplied the new progress value itself rather than play with the scroll speed multiplier.

**12:04** · Waterfall was the same inefficient method as I did with the panda. I just baked two separate textures and swap between two textures instead of using a sprite sheet. Also, here is what it looks like from farther away. So, basically the idea is I baked a single sheet. So, here you can see that I baked a single sheet over here. I used an array modifier just for planning purposes, but I baked a single sheet and I just used them six different times over here.

### Far view of a single sheet of paper acting as the background for the loop transition

**12:30** · I could have instant them for better performance, but I did not do that because I just was it was just not important for this project. But of course, there's like some lighting issues over here, which you could adjust for if you want to, but I didn't do it.

**12:48** · You do see it when you scroll and move your mouse down a little bit on depending on your screen size. But yeah, that's kind of what it looks here. You can see that's how I managed the transition. Then once I get here, all this stuff after I get at a certain point here will shift to the end of this curve as well. I don't know if you can see that over here or not. Oh, no. I do it about like 60% of the way. So you you won't be able to see it, but yeah. So about 70% of the way that's when it starts interacting the shift.

**13:16** · Now some other cool stuff from the other video that I didn't do in this project was you can like bulk compress your images rather than doing it one at a time. So here I again generated this with Gemini I think and basically it's a PowerShell command that you run in your PowerShell and it'll find all the images in your folder and convert them to KTX too. So here you can see that is my basis command over there. I also generated another one that uses image magic to resize to WEBP and 20480 by 2480. I tried both of them, KTX and WEBP.

### AI generated script to bulk convert textures to .KTX2 (repeat from other video)

### AI generated script to bulk convert textures to webp and/or resize with ImageMagick (repeat from other video)

**13:47** · It didn't really matter for that project, but I ended up using WEBP. So, yeah, that's just this one and these both command line tools. Yeah, and that's pretty much it for all the major things.

### Final coding notes

**14:00** · Everything else you see is AI slop code.

**14:02** · Basically, I just asked the AI to attach refs to each object and then just give it some sort of like sign animation over time. time. Now, if you do want a step-by-step tutorial and a lot more in-depth and other techniques, you can check over here. I break everything down in a much more beginner friendly way than this video. Yeah, that's pretty much it for the video. Thanks so much for watching. Take care. Peace out and bye.