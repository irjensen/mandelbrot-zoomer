# mandelbrot-zoomer
A python routine to generate an animation of a mandelbrot zoom. It uses TensorFlow 2.0 to accelerate the matrix arithmetic involved in visualizing the mandelbrot set.
<p align = 'center'>
<img src = 'examples/movie.gif' height = '512px'>
</p>

## Documentation
### Generating a Mandelbrot Zoom
You can run the zoom generator with all default options simply with `python zoom.py`. This will randomly choose a location on the edge of the mandelbrot set to zoom into. Check out the [Flags section](#flags) for different options.

### How does it know where to zoom in?
The Program detects the edges of the mandelbrot set and keeps itself centered there. 
Here is the edge detection in action:
<p align = 'center'>
<img src = 'examples/edges.gif' height = '256px'>
</p>

### Dependancies
- Python 3.6+
- Pillow
- Matplotlib 3.0+
- Numpy
- TensorFlow 2.0+
  - The packages necessary to run TensorFlow
     - Information on how to run TensorFlow on GPU can be found [here](https://www.tensorflow.org/install/)

install dependancies with `pip3 install -r requirements.txt` or `requirements-gpu.txt` if you wish to use tensorflow for gpu

### Flags
- `--max-iterations` the maximum number of times to iterate the algorithm that determines convergence for each frame. Default: `2000`
- `--x-res` resolution of samples along the x-axis. Default: `512`
- `--y-res` resolution of samples along the y-axis. Default: `512`
- `--x-center` x coordinate in the complex plane to start the zoom at. Default: `-0.75`
- `--y-center` y coordinate in the complex plane to start the zoom at. Default: `0`
- `--x-width` starting width of the sample window in the complex plane. Default: `2.5`
- `--y-width` starting height of the sample window in the complex plane. Default: `2.5`
- `--zoom-factor` the factor by which to multiply the window size each frame. Choose <1 for zoom in, >1 for zoom out. Default: `0.8`
- `--frames` number of frames to generate. Default: `100`
- `--save-frames` flag to save each frame of the zoom as a colormapped image file
- `--save-mono` flag to save each frame as a monochrome iamge
- `--format` file format for the saved frames. Can be any file extension supported by Pillow. Example: `jpeg`, `png`, `bmp`, etc. Default: `png`
- `--frames-path` path to the directory in which to store the individual frames. Default: `./frames`
- `--show-edges` flag to render the edge detection along side the mandelbrot zoom
