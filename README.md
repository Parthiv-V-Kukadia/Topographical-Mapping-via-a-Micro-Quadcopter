# Topographical Mapping via a Micro-Quadcopter
This project will describe the design, implementation, and verification of a micro-quadcopter for topographical mapping. The focus of this project is to leverage CrazyFlie’s positioning capabilities for simple topographic mapping of a region of interest.

This is motivated by the need to understand poorly mapped environments, such as the surface of different planets. This could enable the successful landing of other spacecraft, as well as facilitate further exploration of those regions. Topographic mapping has innumerable applications ranging from civilian hiking to military tactical positioning. 

Implementation began with surveying a test area with the drone in a switch-back pattern to ensure full coverage of the test section and collection of positional (x,y,z) information. To increase reliability, the drone was flown forward and backwards over the object filled grid, so that the data was collected twice. The geospatial data collected was then visualized in Python producing an interactive three-dimensional contour plot of the object-filled grid. 

Some challenges had to be overcome, one of which was the inability of the custom observer and controller to fulfill flights within the defined RMSE values. Therefore the stock controller and observer of the CrazyFlie drone were used during the tests. The final visualizations were accurate to the real-world object-filled grid in terms of identifying objects, but not in dimensions. Topographical mapping via a micro-quadcopter provided a detailed visualization of the test grid and can be applied in mapping larger surfaces using a larger quadcopter.

At the end of the project, the team was successfully able to:
1. Engineer a UAV, designing a LQR-based controller and observer to capture data of an object-filled grid, the “unknown terrain”.
2. Utilize drone sensors, avoiding onboard cameras, to collect positional data, refine the mapping process through error correction, and ensure accurate topographical mapping under constrained flight paths and object detection challenges.
3. Process data through Python to build a topographical map that would support search and rescue missions and military operations.
