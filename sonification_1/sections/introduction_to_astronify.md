[<<< Previous](data_preparation.md) | [Next >>>](astronify_testing.md)

# Introduction to Astronify

Developed by Scott Fleming (Space Telescope Science Institute (STScI)), Clara Brasseur (STScI & University of St. Andrews), Jenn Kotler (STScI), and Kate Meredith (GLAS Education), Astronify is a Python package designed to sonify, or represent as sound, a specific type of astronomical data called a light curve. Light curves represent the observed amount of light from an object (typically a star), also called the flux, as it varies over the time of observation. Thus, light curves allow astronomers to observe variability in the amount of light a telescope records coming from a star, or how bright a star appears to us on Earth. Observing this variability can give astronomers insight into all sorts of incredible phenomena, including explosive increases in stellar activity called flares and small, periodic dips in the amount of light observed from a star caused by a planet orbiting that star and blocking some of its light as it passes through our line of sight with the star. We call this latter phenomenon an exoplanet transit, and astronomers have used transits to discover thousands of planets outside our solar system!

Astronify works by mapping the observed flux (the brightness of the star, our dependent variable) to pitch such that higher fluxes are represented by higher pitches. Each observation of the star’s brightness is thus represented by a note where the pitch is controlled by the value of that observation. It is worth noting here that although the default is to have higher fluxes mapped to higher pitches, the user can set a parameter within Astronify to invert the pitches so that higher fluxes are represented by lower pitches. We will discuss the parameters involved in Astronify’s sonifications next week. This will all make sense with some examples.

You can find some [examples of Astronify’s light curve sonifications on the project’s website.]( https://astronify.readthedocs.io/en/latest/)

As a concept check: do you think Astronify is using audification, parameter mapping, or something else entirely?

Here, we’ve discussed Astronify within the context of its intended use: sonifying light curves. However, light curves are just a type 1D data. (Or what I would call 1D in Astronomy, anyway—I suppose a mathematician might tell me that there are two dimensions: time and flux). There are all kinds of 1D data out there, including some of the data you’ve just processed in our earlier tutorials. Before we get to the complicated stuff, though, let’s start with that sonification education we discussed before…

## References

ASTRONIFY: A python package for SONIFYING astronomical data - turning telescope observations into sound! Astronify. Retrieved February 26, 2024, from https://astronify.readthedocs.io/en/latest/

[<<< Previous](data_preparation.md) | [Next >>>](astronify_testing.md)
