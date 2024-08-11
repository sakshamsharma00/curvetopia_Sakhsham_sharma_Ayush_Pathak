This project focuses on detecting and fitting various geometric shapes, with a particular emphasis on star shapes, from input data provided in CSV files. The primary goal is to identify and regularize these shapes, fitting them as accurately as possible to the input data points. The project integrates several key Python libraries, including NumPy, SciPy, and Matplotlib, to handle data manipulation, optimization, and visualization.

### Features

- *Shape Detection*: Identify and fit shapes like stars, circles, ellipses, lines, rectangles, and polygons.
- *Data Handling*: Read and process input data from CSV files.
- *Optimization*: Use advanced mathematical methods to fit shapes to data with minimal error.
- *Visualization*: Graphically display the fitted shapes and the original data points for comparison.
- *Evaluation*: Calculate the accuracy of the fit using metrics such as Mean Squared Error (MSE).

### Library and Method Used

The project utilizes several Python libraries for shape detection and fitting, specifically targeting star shapes. Below are the key libraries and methods employed:

- *NumPy*: For numerical operations and data manipulation.
- *SciPy*: Specifically, the minimize function from scipy.optimize is used for fitting the star shape by minimizing residuals between the given data points and the fitted model.
- *Matplotlib*: Used for plotting and visualizing the fitted star shapes against the input data.

#### Method

1. *CSV Data Reading*: 
   - The read_csv(csv_path) function reads the input CSV file, organizing the data points into structured arrays for further processing. The function groups points based on their paths and segments, enabling a structured approach to shape detection.

2. *Star Shape Fitting*: 
   - The fit_star(x, y, n_arms) function fits a star shape with n_arms arms to the given x and y coordinates. It uses an optimization process to minimize the residuals and determine the best fit. The optimization employs the L-BFGS-B method, a quasi-Newton optimization technique, to find the optimal parameters (center coordinates and arm lengths) for the star shape.

3. *Plotting*:
   - The plot_star_shape(x, y, xc, yc, arms, n_arms) function visualizes the fitted star shape along with the original data points. It plots the detected star shape, showing the center and the arms, and overlays this on the original data for visual comparison. The plot provides insights into how well the fitted model aligns with the input data.

4. *Evaluation*:
   - The evaluate_fit(x, y, xc, yc, arms, n_arms) function computes the Mean Squared Error (MSE) to assess the accuracy of the fit. The MSE quantifies the difference between the original data points and the fitted model, providing a metric for evaluating the fit's precision.

5. *Combined Processing*:
   - The main_combined(csv_path, n_arms=5) function reads the CSV file, combines all path segments into a single array of coordinates, fits a star shape, and evaluates the fitting. It serves as the main function to process an entire image or dataset, generating the fitted star shape and calculating the MSE for the fit.

### Example Usage

To run the code and fit a star shape to your data, simply use the following example:

python
# Example usage for fitting star shape for the whole image
csv_path = 'problems/problems/isolated.csv'
main_combined(csv_path, n_arms=5)


This will read the specified CSV file, fit a star shape to the data, plot the fitted shape, and print the Mean Squared Error of the fit.

### Requirements

- Python 3.x
- NumPy
- SciPy
- Matplotlib

You can install the required libraries using the following pip command:

bash
pip install numpy scipy matplotlib


### Future Enhancements

We will be using **model5** which is based on CNN. Further improvements maybe needed.
Future enhancements may include:

- Extending the detection and fitting capabilities to more complex shapes.
- Improving the optimization algorithms for faster and more accurate fitting.
- Adding support for different file formats beyond CSV.
- Integrating machine learning models to enhance shape detection accuracy.



