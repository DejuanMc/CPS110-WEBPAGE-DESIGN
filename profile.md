# A Bunch of Things.

## A to-do list for my troubles.

1. ~~Draw **two** new characters~~
2. Learn more about GDScript
3. Produce _atleast_ one song
4. Beat stage 20 on **RoR2.**

## Favorite GIFs.

1. ![Sonic Dancing](https://www.sonicstadium.org/uploads/monthly_2025_02/Sonic_Breakdancing.gif.7b65873d3d1ad7033c48ce4b087806ac.gif)

2. ![Chou Kaguya-Hime Crashout](https://c.tenor.com/Z61RtXnfoCsAAAAC/tenor.gif)

3. ![Terrified Perfect Cell](https://c.tenor.com/P98xFE4p6aIAAAAC/tenor.gif)

## HYPERLINKS

### Godot

<a href="https://godot.foundation/">What is Godot</a>

<a href="https://docs.godotengine.org/en/stable/">Godot Documentation</a>

### My Profiles

<a href="https://github.com/DejuanMc">My GitHub Profile</a>

<a href="https://www.youtube.com/@FoxuMusic">My Music Channel</a>
    <img src="https://yt3.googleusercontent.com/puc6Y3JmgrAH12af3icdXXLGBw-81lG03cvr6R-o82YqIpA3WiEiWyXeDct6rOBMCsS1L8fJ=s160-c-k-c0x00ffffff-no-rj" alt="Channel Profile Image" width="50">

## Web Design Tools That I Like

- Visual Studio Code
- GitHub
- PhotoShop
- Adobe

## Quote

> "Bro, do you want to go to-" - 2011x 
>> "Let's go." - Kolossos
>>> "Bro, I didn't even finish speak-" - 2011x
>>>> "LLLet's go." - Kolossos

## GDSCRIPT Code

```
## PLAYER AND GAME INTERACTION SCRIPT IN GDSCRIPT:
extends Node

@export var mob_scene: PackedScene
var score

func _ready() -> void:
	pass

func new_game():
	score = 0
	$Player.start($StartPosition.position)
	$StartTimer.start()
	$HUD.update_score(score)
	$HUD.show_message("Get Ready")
	get_tree().call_group("mobs", "queue_free")

func _on_mob_timer_timeout() -> void:
	# Create a new instance of the mob scene.
	var mob = mob_scene.instantiate()
	
	# Choose a random location on Path2D.
	var mob_spawn_location = $MobPath/MobSpawnLocation
	mob_spawn_location.progress_ratio = randf()
	
	# Set the mob's position to the random location.
	mob.position = mob_spawn_location.position
	
	# Set the mob's direction perpendicular to the path direction.
	var direction = mob_spawn_location.rotation + PI / 2
	
	# Add some randomness to the direction.
	direction += randf_range(-PI / 4, PI / 4)
	mob.rotation = direction
	
	# Choose the velocity for the mob.
	var velocity = Vector2(randf_range(150.0, 250.0), 0.0)
	mob.linear_velocity = velocity.rotated(direction)
	
	# Spawn the mob by adding it to the Main scene.
	add_child(mob)

func _on_score_timer_timeout() -> void:
	score += 1
	$HUD.update_score(score)

func _on_start_timer_timeout() -> void:
	$MobTimer.start()
	$ScoreTimer.start()

func game_over() -> void:
	$ScoreTimer.stop()
	$MobTimer.stop()
	$HUD.show_game_over()
 ```

 ## Semester Milestone:

 - [X] Gain an understanding of HTML.
 - [X] Gain an understanding of CSS.
 - [X] Make use of JSON.
 - [X] Gain an understanding of Markdown.
 - [] Brainstorm Web Design Ideas.
 - [] Create a website with different links to other websites.
 - [] Create a website with cool prompts and buttons.