92% of storage used … If you run out, you can't create, edit, and upload files. Get 100 GB of storage for €1.99 €0.49 for 1 month (personalized price).
import bpy
import math
# Delete default cube
bpy.ops.object.select_all(action='DESELECT')
if bpy.context.object:
 bpy.context.object.select_set(True)
 bpy.ops.object.delete()
# Create a ring (Torus)
bpy.ops.mesh.primitive_torus_add(
 major_radius=1, # Half of the x dimension (2.05m / 2)
 minor_radius=0.04, # Half of the z dimension (0.0565m / 2)
 location=(0, 0, 0)
)


# Get the current object (Torus)
ring = bpy.context.object
# Set initial transformation (frame 0)
ring.location = (0, 0, 0)
ring.rotation_euler = (0, 0, 0)
ring.scale = (0, 0, 0)
# Insert keyframe for initial state
ring.keyframe_insert(data_path="location", frame=0)
ring.keyframe_insert(data_path="rotation_euler", frame=0)
ring.keyframe_insert(data_path="scale", frame=1)
# Set final transformation (frame 360)
ring.location = (0, 0, 0)
ring.rotation_euler = (
 math.radians(360), # Rotation around X axis
 math.radians(720), # Rotation around Y axis
 math.radians(1080) # Rotation around Z axis
)
ring.scale = (1, 1, 1)
# Insert keyframe for final state
ring.keyframe_insert(data_path="location", frame=360)
ring.keyframe_insert(data_path="rotation_euler", frame=360)
ring.keyframe_insert(data_path="scale", frame=360)
# Set up the timeline
bpy.context.scene.frame_start = 0
bpy.context.scene.frame_end = 360
print("Animation created from frame 0 to 360!")
import bpy
import math

# Create a cylinder
bpy.ops.mesh.primitive_cylinder_add(
 radius=0.00, # Radius for the x and y dimensions
 depth=2, # Depth for the z dimension
 location=(0, 0, 0)
)
 # Get the current object (cylinder)
cylinder = bpy.context.object
# Set scale
cylinder.scale = (1, 1, 1)
# Set rotation in degrees (convert to radians)
cylinder.rotation_euler = (
 math.radians(540), # Rotation around X axis
 math.radians(2160), # Rotation around Y axis
 math.radians(3240) # Rotation around Z axis
)
# Set location
cylinder.location = (0, 0, 0)
# Apply transformations
bpy.ops.object.transform_apply(location=False, rotation=True, scale=True)
print("Cylinder created with the desired properties!")

# Create a cylinder
bpy.ops.mesh.primitive_cylinder_add(
 radius=0.04, # Radius for the x and y dimensions
 depth=2, # Depth for the z dimension
 location=(0, 0, 0)
)
# Get the current object (cylinder)
cylinder = bpy.context.object
# Set initial transformation (frame 0)
cylinder.scale = (0, 0, 0)
cylinder.rotation_euler = (0, 0, 0)
# Insert keyframes for initial state
cylinder.keyframe_insert(data_path="scale", frame=0)
cylinder.keyframe_insert(data_path="rotation_euler", frame=0)
# Set final transformation (frame 360)
cylinder.scale = (1, 1, 1)
cylinder.rotation_euler = (
 math.radians(540), # Rotation around X axis
 math.radians(2160), # Rotation around Y axis
 math.radians(3240) # Rotation around Z axis
)
# Insert keyframes for final state
cylinder.keyframe_insert(data_path="scale", frame=360)
cylinder.keyframe_insert(data_path="rotation_euler", frame=360)
# Set up the timeline
bpy.context.scene.frame_start = 0
bpy.context.scene.frame_end = 360
print("Cylinder animation created from frame 0 to 360!")
# results of intersects "Torus" and "Cylinder" equation : image (44,87,109,110,123)
