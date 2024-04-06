
# A Way Through the Forest
![Schermafbeelding_2024-04-06_090039](https://github.com/Bambaclad1/A_way_through_the_forest/assets/67043806/15f7dc8b-92b4-40b3-b80f-68e8a4ea7333)

A Way Through the Forest is a horror game, and it is inspired by that goofy slenderman game on your device. Although, there is more lore behind it, and thus, you explore different forests. Your only goal is to make it out alive, and try to survive. Good luck, you'll need it.

Hi! My name is Raman, and this is my game. I will give you a disclaimer, and that is to please mind my broken English. English is not my main language, and especially grammar is a subject I suck at. But I try my best!
While I speak Dutch, I find it more convenient to explain this in English, because of  the sake of unity engine being a English program.

My first project was supposed to be a FPS shooter, largely inspired by Superhot, but I scrapped it as my knowledge of scripting was pretty weak. So I had some thinking going on.
I decided to make a horror game experience, not only can I easily fit in a story with visuals, it would also be convenient for me to create, because of horror games having tons of trigger areas, which give creepy visuals to the game itself, and I took my time learning how those trigger areas work.

My game name is: A Way Through the Forest, and the gameplay is exactly the title.
My focus is to make a storyline on this, and have the forests have different visuals, for example, a cherry tree area, which gives Japan vibes to it, but also try to extend forests, to include epic houses you can discover and interact with.



## Contents

- Gameplay
- Mechanics
- Scripts
- Version Logging
- FAQ
- Developer's Notes

## Gameplay
The gameplay is in a first person perspective. You as player 1 (bean), is venturing a forest. You eventually find a wooden medieval house, where there is a cracking chair, and a grandpa/entity is sitting.
You have one simple goal. Don’t die. The game will introduce you to scary and fatal situations where you most likely try to survive out of. I want to add some sense of humor to the game because hey, a horror game doesn’t need to be that serious 😉
Anyways, your first experience is going to be a prologue chapter. It is a Chapter zero which is intended to give you a feel of how the game is going to be. I want to put all my creativity and toss it in this project, just like I did with my Visual Studio C-Sharp project: Bamba’s Text RPG.

## Mechanics 
The mechanics for this game is as simple as wasd to move, jump to jump, and running!
## Scripts
This section will go in-depth and cover the scripts.
The movement is handled by a asset called FirstPlayerController, so that is unrelevant to discuss.

---



BlinkingLights.cs -  Handles the blinking lights for a *spooky* feeling.
```
using System.Collections; 
using System.Collections.Generic;
using UnityEngine;

public class BlinkingLights : MonoBehaviour
{
    public float flickerIntensity = 0.2f;
    public float flickersPerSecond = 3.0f;
    public float speedRandomness = 1.0f;

    private float time;
    private float startingIntensity;
    private Light light;
    void Start()
    {
        light = GetComponent<Light>();
        startingIntensity = light.intensity;
    }

    // Update is called once per frame
    void Update()
    {
        time += Time.deltaTime * (1 - Random.Range(-speedRandomness, speedRandomness)) * Mathf.PI;
        light.intensity = startingIntensity + Mathf.Sin(time * flickersPerSecond) * flickerIntensity;

    }
}
```
```
    public float flickerIntensity = 0.2f;
    public float flickersPerSecond = 3.0f;
    public float speedRandomness = 1.0f;
```
Here, i will create data types, 3 floats. It's pretty obvious what they are used for.
```
    private float time;
    private float startingIntensity;
    private Light light;
```
Here, i will make some invisible data types which will be able to manipulate the light to my willings.
```
    void Start()
    {
        light = GetComponent<Light>();
        startingIntensity = light.intensity;
    }
```
This is the first thing that unity will do, and that is also pretty obvious, saying that the datatype i made will be the same as the intensity of the light itself.
```
    void Update()
    {
        time += Time.deltaTime * (1 - Random.Range(-speedRandomness, speedRandomness)) * Mathf.PI;
        light.intensity = startingIntensity + Mathf.Sin(time * flickersPerSecond) * flickerIntensity;

    }
```
Every frame, it will run a calculation with time and a random range which is dependent on the value you put as speedRandomness.
Then, it will say that the current intensity of the light, is the one you start with, and a calculation which multiplies time with the amount of flickers of the light you want it to be multiplied with the intensity you put.

And this creates a nice blinking effect.

---
Footstep

## Version Logging
v0.30-alpha - alpha release of the game for people to try out

## FAQ
you

# Developer Notes

