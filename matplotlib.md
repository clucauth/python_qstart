# Matplotlib


## Basic usage

    import matplotlib.pyplot as plt
    import numpy as np
  
    fig, ax = plt.subplots()  # Create a figure containing a single axes.
    ax.plot([1, 2, 3, 4], [1, 4, 2, 3])  # Plot some data on the axes.
    plt.show()
    
The easiest way to create a new figure is with pyplot:

    fig = plt.figure()  # an empty figure with no Axes
    fig, ax = plt.subplots()  # a figure with a single Axes
    fig, axs = plt.subplots(2, 2)  # a figure with a 2x2 grid of Axes
    
Two ways to plot: OOP and Method-call

OOP:

    x = np.linspace(0, 2, 100)

    # Note that even in the OO-style, we use `.pyplot.figure` to create the figure.
    fig, ax = plt.subplots()  # Create a figure and an axes.
    ax.plot(x, x, label='linear')  # Plot some data on the axes.
    ax.plot(x, x**2, label='quadratic')  # Plot more data on the axes...
    ax.plot(x, x**3, label='cubic')  # ... and some more.
    ax.set_xlabel('x label')  # Add an x-label to the axes.
    ax.set_ylabel('y label')  # Add a y-label to the axes.
    ax.set_title("Simple Plot")  # Add a title to the axes.
    ax.legend()  # Add a legend.
    
Method-call:

    x = np.linspace(0, 2, 100)

    plt.plot(x, x, label='linear')  # Plot some data on the (implicit) axes.
    plt.plot(x, x**2, label='quadratic')  # etc.
    plt.plot(x, x**3, label='cubic')
    plt.xlabel('x label')
    plt.ylabel('y label')
    plt.title("Simple Plot")
    plt.legend()
    
In general, we suggest to restrict pyplot to interactive plotting (e.g., in a Jupyter notebook), and to prefer the OO-style for non-interactive plotting (in functions and scripts that are intended to be reused as part of a larger project).

