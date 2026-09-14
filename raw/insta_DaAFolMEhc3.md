---
source: https://www.instagram.com/reel/DaAFolMEhc3/
plateforme: Instagram
genre: video
auteur: NextWork | Learn AI
duree_s: 135.74400329589844
traite_le: 2026-09-08
statut: brut
---

# Video by itsnextwork

## Description
GTA VI system design before GTA VI 

Follow & Comment "Projects" for hands-on projects to add to your resume! 

#systemdesign

## Transcription audio
In today's system design interview, I want you to explain how we load the entire city in GTA 6 without a loading screen. Oh, easy, bro. We just load the entire map into memory when it boots. Then it's just sitting there. Let's go. The entire city into memory? A map that big doesn't come close to fitting on a console's RAM. The game is gonna crash before we even make it to the strip. The airway, the airway. Oh yeah, okay. My bad, forget that. Okay, we don't load the whole world at once. What if we load only a slice around the player and we swap pieces in and out as they move? So you're not loading the city, you're loading a moving window as I walk around. Exactly, it's called streaming the world. We chopped the whole map into a grid of tile. The only ones loaded into memory are the tiles near the actual player. Everything else is just sitting on the disk, not loaded yet. Wait, so most of the city isn't even loaded while I'm playing? It's the same thing that Google Maps does. When you drag the map around, it only goes to squares on your screen, not everything else. We're doing that except with a 3D city that's never gonna get released. Okay, but picture Franklin flooring it down the freeway at 120. The next tile isn't gonna be loaded, so what does he do? Just drive into a black hole. That's why we don't just load what's around him. We load ahead of him too, in the direction that he's actually driving. The faster he goes, the further we load. So the road is always built before he gets there. And what if he whips a U-turn in his Bugatti? We cancel the tiles we're about to load and we start pulling the ones in front of him. What about the skyline? I can see buildings that are loaded from far away. You're telling me those aren't loaded properly. What you see in the distance is an actual building. It's basically like a cheap cardboard cutout. It has almost no detail. A fake building? As you get closer, we make it sharper and more detailed. The real thing only loads when you're really up close to it. That's called level of detail. So what stops all these tiles from just piling up in memory while I drive around? We've got a fixed memory budget. Picture like a backpack that only holds so much. Every time we load a new tile, one that's now out of range gets dropped to make more room. The world is never fully there. It gets built and tore down as we go. And this only works now like we couldn't have done this on older consoles? Well, the disc was the bottleneck. Old hard drives were slow, so we hit the loading. That's why old games stuck you in a slow elevator, buying time to load the next area. New consoles read off SSD, which is fast enough to stream the city as we drive. Look, where are you learning this from, intern? Well, while I'm waiting for GTA 6 to come out, I just go to learn.nexcliff.org and I do a bunch of hands-on projects. I can either choose from all of these or I can actually create my own one like I did on GTA 6. Damn, we literally got the world's best way to learn before GTA 6. For free.

## Images
- images/insta_DaAFolMEhc3_1.jpg
- images/insta_DaAFolMEhc3_2.jpg
- images/insta_DaAFolMEhc3_3.jpg
