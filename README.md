# TaMag: Magnetogram Transformation Module

<!-- ![TaMag Logo](tamag_logo.png) -->

TaMag is a Python module designed for transforming magnetogram maps using various techniques that reduce information loss. This module is particularly useful for augmenting magnetograms, addressing data imbalance for predictive modeling.

## Installation

TaMag requires Python (>= 3.9) and the following dependencies:
- numpy (>=1.17.0)
- scipy (>=1.3.0)
- astropy (>=5.0.6,!=5.1.0)

Install TaMag using pip:
```bash
pip install tamag
```

or using conda:
```bash
conda install -c conda-forge tamag
```

## Usage Example

```python

from tamag.transforms import Flip
from tamag.datasets import load_fits_data
import warnings
warnings.filterwarnings("ignore")
import matplotlib.pyplot as plt

# Create an instance of the transformer
transformer = Flip(direction='vertical')

# Load a sample magnetogram
magnetogram, magnetogram_header, bitmap  = load_fits_data()

# Transform the magnetogram
transformed_magnetogram = transformer.transform(magnetogram,scale=255,rgb=True)

# Display the results
plt.figure(figsize=(15, 5))
plt.subplot(1, 2, 1)
plt.imshow(magnetogram, cmap='gray')
plt.title('Original Image')

plt.subplot(1, 2, 2)
plt.imshow(transformed_magnetogram, cmap='gray')
plt.title('Flipped Image')

```

## Documentation

For detailed documentation and examples, visit the [TaMag Documentation](https://bitbucket.org/gsudmlab/tamag/src/master/docs/examples/TRANSFORMER.md).

## Changelog

See the [Changelog](https://bitbucket.org/gsudmlab/tamag/src/master/CHANGELOG.md) for information about notable changes.

<!-- ## Contributing

We welcome contributions from the community. Refer to the [Contributing Guide](https://github.com/tamag/tamag/blob/main/CONTRIBUTING.md) for more details. -->

## License

TaMag is distributed under the GNU License. See [GNU General Public License, Version 3](https://bitbucket.org/gsudmlab/tamag/src/master/LICENSE.txt)   for details.


## Citation

If you use TaMag in a scientific publication, please consider citing our work. Refer to the [Citation Guide](https://tamag.example.com/citation) for details.

## Acknowledgment

This work was supported by NSF Grant Award 2104004.

***

This software is distributed using the [GNU General Public License, Version 3](https://bitbucket.org/gsudmlab/tamag/src/master/LICENSE.txt)  
![GNU GPL v3 License](https://bitbucket.org/gsudmlab/tamag/src/master/docs/images/gplv3-88x31.png)


***

© 2024 Temitope Adeyeha, Chetraj Pandey, Berkay Aydin

[Data Mining Lab](http://dmlab.cs.gsu.edu/)

[Georgia State University](http://www.gsu.edu/)
