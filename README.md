# DSV Browser

A web application for visualizing interconnections between Data Specification Vocabulary (DSV) enabled specifications and their relationships.

## Overview

DSV Browser helps you understand how different data specifications relate to each other by:

- **Live loading** of specifications from URLs
- **Parsing DSV metadata** from specification documents  
- **Visualizing relationships** between specifications that profile or reuse terms from others
- **Interactive network graphs** showing dependencies and connections
- **Exploring specification hierarchies** in data standardization ecosystems

## Quick Start

```bash
npm install
npm run dev
```

Then open `http://localhost:3000` in your browser.

## Features

### 🔍 Live Specification Loading
- Load specifications directly from URLs
- Predefined sample specifications (DCAT-AP, DCAT-DAP, DSV-DAP, DSV)
- Automatic DSV metadata detection and parsing
- Support for JSON-LD embedded metadata and linked DSV files
- RDF vocabulary title extraction from Turtle, JSON-LD, and RDF/XML formats
- Fallback to basic HTML parsing when DSV is not available

### 📊 Interactive Visualization
- Network graph visualization using vis-network
- Node colors indicating specification types (Application Profiles, Vocabularies, Standards)
- Interactive tooltips with specification details
- Legend showing node types and colors
- Responsive design for desktop and mobile

### 📈 Relationship Analysis
- Profiles hierarchy visualization (which specifications profile others)
- Dependency tracking (which vocabularies/ontologies are reused)
- Connected component analysis
- Search and filter capabilities

### 🎯 DSV Specification Support
- Application Profiles (dsv:ApplicationProfile)
- Vocabularies and Ontologies (prof:Profile, owl:Ontology)
- Property and Class profiles
- Property value reuse relationships

## Getting Started

### Prerequisites
- Node.js (v16 or higher)
- Modern web browser with ES6 module support

### Installation

1. Clone the repository:
```bash
git clone https://github.com/jakubklimek/dsv-browser.git
cd dsv-browser
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

4. Open your browser to `http://localhost:3000`

### Production Build
```bash
npm run build
npm run preview
```

## Usage

### Loading Specifications

1. **Enter a specification URL** in the input field (e.g., `https://mff-uk.github.io/specifications/dcat-ap/`)
2. **Click "Add Specification"** to parse and add it to the visualization
3. **Use "Load Samples"** to quickly load example DSV-enabled specifications

### Exploring the Network

- **Click nodes** to select and highlight connected specifications
- **Double-click** to focus on a specific specification
- **Drag** to reposition nodes
- **Zoom and pan** to explore different areas of the network
- **Hover** over nodes and edges for additional information

### Understanding the Visualization

#### Node Colors
- **Blue** (#667eea): Application Profiles
- **Green** (#48bb78): Vocabularies and Ontologies  
- **Orange** (#ed8936): Standards and Specifications
- **Purple** (#9f7aea): Other resources

#### Edge Types
- **Solid arrows**: Direct profiling relationships ("profiles")
- **Dashed arrows**: External dependencies (specifications not loaded)

## DSV Support

The application understands the following DSV concepts:

### Supported Metadata Formats
- **JSON-LD** embedded in HTML `<script>` tags
- **Linked DSV files** (`.jsonld`, `.ttl` formats)
- **Common DSV file patterns** (`/dsv.jsonld`, `/metadata.jsonld`)

### Parsed Relationships
- `prof:isProfileOf` - Specification profiling relationships
- `dsv:profileOf` - Term profile relationships  
- `dsv:reusedFromResource` - Property value reuse
- `hasArtifact` - Resource dependencies

### Example DSV-enabled Specifications
- [DCAT-AP 3.0.1](https://mff-uk.github.io/specifications/dcat-ap/)
- [DCAT 3 Default Application Profile](https://mff-uk.github.io/specifications/dcat-dap/)
- [DSV-DAP](https://mff-uk.github.io/data-specification-vocabulary/dsv-dap/)
- [DSV Core](https://mff-uk.github.io/data-specification-vocabulary/dsv/)

## Architecture

### Core Components

- **`DSVParser`** - Parses DSV metadata from various sources and formats
- **`SpecificationManager`** - Manages specification loading, storage, and relationships
- **`NetworkVisualizer`** - Creates interactive network visualizations
- **`main.js`** - Application orchestration and UI event handling

### Technology Stack
- **Vite** - Build tool and development server
- **vis-network** - Interactive network visualization
- **Native ES6 modules** - No framework dependencies
- **JSON-LD** processing for semantic metadata

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Related Resources

- [Data Specification Vocabulary (DSV)](https://w3id.org/dsv/)
- [DSV Default Application Profile](https://mff-uk.github.io/data-specification-vocabulary/dsv-dap/)
- [Sample DSV Specifications](https://mff-uk.github.io/specifications/)
- [Dataspecer Tool](https://dataspecer.com/)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
Browser of specifications implementing the Data Specification Vocabulary
