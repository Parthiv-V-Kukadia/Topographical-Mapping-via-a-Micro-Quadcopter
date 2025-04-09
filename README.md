# Topographical Mapping via a Micro-Quadcopter

This project details the design, implementation, and verification of a micro-quadcopter system for topographical mapping. The primary objective is to utilize the positioning capabilities of the CrazyFlie drone to perform simple topographic mapping of a defined region.

## Motivation

The motivation behind this project stems from the need to understand and map poorly accessible or uncharted environments, such as the surfaces of other planets. Accurate topographical data is crucial for the successful landing of spacecraft and for facilitating further exploration. Furthermore, topographic mapping has a wide range of terrestrial applications, from civilian uses like hiking trail mapping to military applications such as tactical positioning and reconnaissance.

## Implementation

The implementation involved surveying a designated test area using the CrazyFlie drone. A systematic switch-back flight pattern was employed to ensure comprehensive coverage of the test section and the collection of positional data in three dimensions (x, y, z). To enhance the reliability of the collected data, the drone was flown both forward and backward over the object-filled grid, effectively doubling the data points for each location.

The acquired geospatial data was subsequently processed and visualized using Python. This process generated an interactive three-dimensional contour plot representing the topography of the object-filled grid.

## Challenges and Solutions

One significant challenge encountered during the project was the suboptimal performance of the custom-designed observer and controller, which did not meet the defined Root Mean Square Error (RMSE) requirements for stable flight. As a result, the decision was made to utilize the stock controller and observer provided by the CrazyFlie firmware for the data collection flights.

The final topographical visualizations successfully identified the presence and general locations of objects within the test grid. However, the dimensional accuracy of the mapped objects was not precise.

## Conclusion

The topographical mapping system implemented using a micro-quadcopter successfully provided a detailed visualization of the test grid. This demonstrates the potential of using small UAVs for mapping surfaces. With the use of a larger quadcopter and further refinements, this approach can be scaled to map larger and more complex terrains.

## Project Outcomes

At the conclusion of this project, the team successfully:

* **Engineered a UAV system** by designing an LQR-based controller and observer (although the stock controller was ultimately used for data collection) to capture data of an object-filled grid, representing "unknown terrain."
* **Utilized drone sensors**, specifically avoiding onboard cameras and relying on positional data, to collect geospatial information. The mapping process was refined through error consideration to ensure relatively accurate topographical mapping despite constrained flight paths and object detection challenges.
* **Processed data using Python** to generate a topographical map with the potential to support applications such as search and rescue missions and military operations.

## Code

The primary Python script used for controlling the drone and logging data is available in this repository (`flight.py`).

## Jupyter Notebook

The data collected from the drone flights was processed and visualized using a Jupyter Notebook (`mapping_final.ipynb`). This notebook contains the code for:

* Loading the logged data from the JSON file.
* Extracting the positional (x, y, z) data.
* Generating a three-dimensional scatter plot of the data points.
* Creating an interactive contour plot to visualize the topography of the mapped area.

**Note:** Due to the nature of Jupyter Notebooks, the content is typically viewed directly in a web browser. Please refer to the `mapping_final.ipynb` file for the detailed data processing and visualization code.

## Getting Started

To replicate this project, you will need the following:

1.  **Hardware:**
    * A CrazyFlie 2.1 micro-quadcopter.
    * A compatible radio dongle for communication with the CrazyFlie.
    * A computer with USB connectivity for the radio dongle.
    * A controlled indoor environment for flight testing.
    * An object-filled grid or a region of interest for topographical mapping.

2.  **Software:**
    * Python 3.x installed on your computer.
    * The `cflib` Python library for controlling the CrazyFlie. You can install this using pip: `pip install cflib`
    * Jupyter Notebook installed for viewing and running the data processing and visualization script. You can install this using pip: `pip install notebook`
    * The `numpy` library for numerical operations in Python: `pip install numpy`
    * The `matplotlib` library for plotting in Python: `pip install matplotlib`
    * The `scipy` library for scientific computing, particularly for contour plotting: `pip install scipy`
    * A text editor or IDE for viewing and editing the Python scripts.

3.  **Setup:**
    * Ensure your CrazyFlie drone is properly assembled and charged.
    * Connect the radio dongle to your computer.
    * Install the necessary Python libraries as listed above.

4.  **Usage:**
    * **Drone Control and Data Logging:** Modify the `uri` variable in the provided Python script (`.py` file) to match the radio channel of your CrazyFlie. Run the script to connect to the drone and execute the flight pattern for data collection. The positional data will be saved to a `hardware_2_data.json` file (or a similar named file).
    * **Data Processing and Visualization:** Open the `mapping_final.ipynb` file using Jupyter Notebook. Follow the instructions within the notebook to load the collected data, process it, and generate the topographical maps. You may need to adjust file paths within the notebook to match where you saved the data.

**Important Notes:**

* Always exercise caution when flying the drone and ensure a safe testing environment.
* The accuracy of the topographical map is dependent on the flight stability and the precision of the CrazyFlie's positioning system.
* The provided code includes a section for a custom controller and observer, which was not used in the final data collection. This code can be further explored and debugged for potential future use.

