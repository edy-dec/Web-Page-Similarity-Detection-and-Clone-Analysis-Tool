# Web Page Similarity Detection and Clone Analysis Tool

A sophisticated Python-based web analytics tool that automatically detects and groups similar HTML pages using multi-dimensional similarity analysis, machine learning techniques, and computer vision.

## Overview

This tool analyzes web pages across multiple dimensions to identify clones, duplicates, and similar content patterns. It combines text analysis, DOM structure comparison, CSS styling evaluation, and visual similarity detection to provide comprehensive webpage similarity scoring.

## Key Features

### Multi-Dimensional Analysis
- **Text Content Analysis**: TF-IDF vectorization with cosine similarity for semantic text comparison
- **DOM Structure Analysis**: HTML tag distribution and structural pattern recognition
- **CSS Style Extraction**: Visual styling and CSS class usage pattern comparison
- **Visual Similarity Detection**: Automated screenshot capture and perceptual hash comparison

### Advanced Capabilities
- **Multi-Factor Scoring System**: Weighted similarity algorithm combining:
  - Text content (50%)
  - DOM structure (20%)
  - CSS styles (20%)
  - Visual appearance (10%)
- **Automated Clustering**: Groups similar pages with configurable similarity thresholds
- **Scalable Processing**: Handles large-scale HTML datasets across multi-tier directory structures

## Technologies

### Core Technologies
- Python 3.x
- BeautifulSoup4 - HTML parsing and DOM analysis
- Selenium WebDriver - Browser automation
- scikit-learn - Machine learning algorithms

### Machine Learning & Computer Vision
- TF-IDF vectorization
- Cosine similarity metrics
- Clustering algorithms
- OpenCV - Image processing
- ImageHash - Perceptual hashing
- PIL (Pillow) - Image manipulation

### Data Processing
- NumPy - Numerical computing
- NetworkX - Graph-based analysis
- JSON - Report generation

## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/webpage-similarity-detector.git
cd webpage-similarity-detector

# Install required packages
pip install -r requirements.txt

# Download ChromeDriver for Selenium
# Ensure ChromeDriver matches your Chrome browser version
```

### Requirements

```txt
beautifulsoup4>=4.12.0
selenium>=4.15.0
scikit-learn>=1.3.0
opencv-python>=4.8.0
imagehash>=4.3.1
Pillow>=10.0.0
numpy>=1.24.0
networkx>=3.1
lxml>=4.9.0
```

## Usage

### Basic Usage

```python
from similarity_detector import WebPageAnalyzer

# Initialize the analyzer
analyzer = WebPageAnalyzer(similarity_threshold=0.75)

# Analyze HTML files in a directory
results = analyzer.analyze_directory('path/to/html/files')

# Generate similarity report
analyzer.generate_report(results, 'similarity_report.json')
```

### Advanced Configuration

```python
# Customize similarity weights
analyzer = WebPageAnalyzer(
    text_weight=0.5,
    dom_weight=0.2,
    css_weight=0.2,
    visual_weight=0.1,
    similarity_threshold=0.80
)

# Process multi-tier directory structure
results = analyzer.analyze_tiered_structure('path/to/tier1')

# Export clustering results
clusters = analyzer.cluster_similar_pages(results)
analyzer.export_clusters(clusters, 'clusters.json')
```

### Command Line Interface

```bash
# Analyze a directory of HTML files
python analyzer.py --input ./html_files --output report.json --threshold 0.75

# Process with visual analysis disabled (faster)
python analyzer.py --input ./html_files --no-visual --output report.json

# Generate detailed clustering report
python analyzer.py --input ./html_files --cluster --output clusters.json
```

## Project Structure

```
webpage-similarity-detector/
│
├── src/
│   ├── analyzer.py          # Main analysis engine
│   ├── text_analyzer.py     # TF-IDF and text comparison
│   ├── dom_analyzer.py      # DOM structure analysis
│   ├── css_analyzer.py      # CSS style extraction
│   ├── visual_analyzer.py   # Screenshot and image comparison
│   └── clustering.py        # Clustering algorithms
│
├── tests/
│   ├── test_analyzer.py
│   └── test_similarity.py
│
├── examples/
│   ├── basic_usage.py
│   └── advanced_clustering.py
│
├── requirements.txt
├── README.md
└── LICENSE
```

## How It Works

### 1. Text Content Analysis
Extracts visible text from HTML pages and uses TF-IDF vectorization to create document vectors. Calculates cosine similarity between vectors to determine semantic similarity.

### 2. DOM Structure Analysis
Analyzes the distribution and frequency of HTML tags, creating a structural fingerprint for each page. Compares tag patterns to identify pages built from similar templates.

### 3. CSS Style Extraction
Extracts CSS classes, inline styles, and style patterns. Compares styling approaches to identify pages with similar visual design systems.

### 4. Visual Similarity Detection
Uses Selenium to capture page screenshots in a headless browser. Generates perceptual hashes using ImageHash and compares visual appearance directly.

### 5. Multi-Factor Scoring
Combines all similarity metrics using configurable weights to produce a final similarity score between 0 and 1.

### 6. Clustering
Groups pages with similarity scores above the threshold, creating clusters of related or duplicate content.

## Use Cases

- **SEO Auditing**: Identify duplicate content issues across websites
- **Web Content Analysis**: Detect template-based websites and common patterns
- **Competitor Analysis**: Find similar pages across different domains
- **Quality Assurance**: Detect unintended page duplication in large sites
- **Research**: Analyze web page evolution and template usage patterns

## Performance Considerations

- Visual analysis is computationally expensive; disable for faster processing of large datasets
- Adjust similarity thresholds based on your specific use case
- Use multi-processing for large-scale analysis
- Cache screenshot results to avoid repeated rendering

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Built with scikit-learn for machine learning capabilities
- Selenium WebDriver for browser automation
- ImageHash for perceptual hashing implementation
- BeautifulSoup for HTML parsing

## Contact

Your Name - [@yourtwitter](https://twitter.com/yourtwitter)

Project Link: [https://github.com/yourusername/webpage-similarity-detector](https://github.com/yourusername/webpage-similarity-detector)

---

**Note**: This tool is designed for legitimate web analysis purposes. Please respect robots.txt files and website terms of service when analyzing web content.
