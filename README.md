
# gdtxt

Purpose: An attempt to manually create a godot project and see if it will run in godot 4.0

Reason: I made a godot project, added some stuff, then looked at the resulting files in a text editor. They're pretty readable. I bet it could be done manually.

Structure
---

project.godot

Having to use a generated project.godot, hard to tell what's wrong with it.

```
; Engine configuration file.
; It's best edited using the editor UI and not directly,
; since the parameters that go here are not all obvious.
;
; lol
;
; Format:
;   [section] ; section goes between []
;   param=value ; assign values to parameters

config_version=5
; What are the differences between config versions?
; I'll keep the 5 since the rest are related to this config version.

[application]

config/name="projectName"
config/features=PackedStringArray("godotVersion", "Mobile")
; In this case, 4.0
; Don't remember what the PC only one is called.

config/icon=:res://icon.svg"

[rendering]
renderer/rendering_method="mobile"
; Seems like other rendering methods can be used.
```

scene.tscn

```
[gd_scene loadsteps=2 format=3]
; Docs says loadsteps doesn't matter, but should = # of resources.

; Doesn't mention what format is about, it's 2 in docs but 3 here.
; Probably best not to touch it for now.

[ext_resource type="Texture2D" path="res://icon.svg" id="icon"]
; uid's can't be arbitrary, considered invalid.
; uid's unneeded to load. 
; It'll add it's own if saved in the editor. 
; Probably makes loading faster or something.

[node name="Level" type="Node2D"]

[node name="Icon" type="Sprite2D" parent="."]
; First node is root, not sure if can be multiple roots.
; Use . for child of root, use names for child of child.

texture = ExtResource("icon")
position = Vector2(100, 100)
```

.godot directory 

- Generated on load.
