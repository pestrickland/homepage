title: Using Scripts with Blender
summary: I used Blender's scripting functionality to look at trajectories in 3D. After writing a very simple script I was able to import trajectory data and plot it as a series of spheres. It looks promising and I will do more work to extend its functionality in the future.
tags: Blender, Python
date: 20140712

I've been playing with [Blender](http://www.blender.org/ "blender.org") --  free and open source modelling software -- on and off for a while. I spent most of that time trying to make 3D models, hoping to produce a 3D model of the different aircraft that I work with.

More recently I started to look into the scripting possibilities that Blender offers. I saw it used to produce some high quality scientific visualisations and wondered if I could put it to good use. With that in mind, I looked at importing some trajectory data into Blender.

## Assessing trajectories

One of the main areas I look at in my job is dropping or firing things from aircraft. And one important part of that is making sure that once you've dropped something, it doesn't come back to hit you.

Recently I was looking at some trajectory data that was presented as 2D graphs. One graph showed a view from above the aircraft, and another showed the side view. In the vast majority of cases it was quite clear that an object fell away cleanly and didn't endanger the aircraft, but sometimes it isn't that clear.

Using 2D graphs to see what is happening can be confusing, so I decided to plot the data in 3D, and rather than use Excel or matplotlib, I tried Blender.

### Looking for a script

Not wanting to learn everything from scratch, I looked aroud for something I could use and found an example produced by [Mathieu Gibert](http://www.gibert.biz/downloads/3dscatterplotswithblender "3D scatter plots with Blender"). I was able to replicate his plots using his example data, but I couldn't substitute my own data for some reason. Despite that, his script still provided enough information for me to have a go at something a bit simpler:

    :::Python3
    import bpy
    import csv

    def add_sphere(location, diameter):
        """Add a sphere."""
        bpy.ops.mesh.primitive_uv_sphere_add(size=diameter,
                                             location=location)

    def add_cuboid(location, dimensions):
        """Add a cuboid."""
        bpy.ops.mesh.primitive_cube_add(radius=1,
                                        location=location)

    # Import trajectory from file.
    raw_file = "/home/paul/workspace/traj.csv"
    diameter = 0.5  # Set a nominal diameter for now.

    locx, locy, locz = ([] for i in range(3))
    with open(raw_file) as f:
        csv_data = csv.reader(f)
        for line in csv_data:
            x, y, z = [float(i) for i in line]
            add_sphere(location=(x, y, z), diameter=diameter)

The script above is very simple. I defined two functions that use the [Blender `bpy` API](http://www.blender.org/documentation/blender_python_api_2_70_release/contents.html "Blender 2.70 API documentation") to generate spheres and cuboids. Each of the Blender methods has many more parameters than I've used here, but this was just a proof of concept for me, so I simply gave each object a size and location.

The rest of the script opens a CSV file, converts each line into $\left(x, y, z\right)$ coordinates and generates a sphere using my function. I used the `with` statement to handle opening and closing the file nicely, as written about at [Bite Sized Python Tips](http://freepythontips.wordpress.com/2014/01/15/the-open-function-explained/ "The open function explained").

I didn't make use of the `add_cuboid` function when I did this initial work. Instead I added one manually. The cuboid is used to represent the aircraft. It is basically a "collision box" that completely contains the aircraft. If an object enters that box, a collision is considered to have occurred.

The images below show the benefit of having a 3D view. From the top and side, a collision looks possible, but in 3D it can be seen that this is narrowly avoided.

<figure>
<img src="/images/blender_traj_side.jpg" title="Side view of collision box">
<figcaption>In this view it looks like the trajectory enters the collision box.
</figcaption>
<img src="/images/blender_traj_top.jpg" title="Top view of collision box">
<figcaption>Again, a collision looks possible.
</figcaption>
<img src="/images/blender_traj_3D.jpg" title="3D view of trajectory">
<figcaption>The 3D view shows that the trajectory just misses the box.
</figcaption>
</figure>

The example above is quite a contrived one, but it was useful to get the basics sorted out.

### Future

The Blender API has much more functionality than I've used so far. Here are some ideas I have for future work:

* Set object size in input file
* Change individual spheres into a continuous ribbon or tube
* Turn script into Blender addon including its own panel

Ideally I would end up with a whole suite of useful tools in Blender that could be used both for analysis and producing high quality graphics for reports. Based on my limited exploration so far, I think it might be possible.
