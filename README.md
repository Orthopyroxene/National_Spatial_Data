# 🇦🇺 Australian National Spatial Data Services Directory

![License](https://img.shields.io/badge/license-CC%20BY%204.0-blue.svg)
![Services Monitored](https://img.shields.io/badge/services-450%2B-green.svg)
![Last Updated](https://img.shields.io/badge/updated-daily-brightgreen.svg)

## 🎯 About

The Australian National Spatial Data Services Directory is a comprehensive, curated collection of spatial data portals, web services, APIs, and interactive mapping applications across Australia. Rather than hosting data directly, this repository serves as a centralized directory to help users discover and access Australia's rich ecosystem of geospatial services.

## 🌟 What We Provide

### 📋 Comprehensive Service Catalogs
- **500+ Web Services**: REST APIs, WMS/WFS endpoints, and data services
- **200+ Data Portals**: Open data catalogs from all levels of government
- **150+ Web Maps**: Interactive mapping applications and viewers
- **100+ Specialized Tools**: Sector-specific applications and services

### 🏛️ Complete Government Coverage
- **Federal Agencies**: Geoscience Australia, ABS, Department of Infrastructure
- **All States & Territories**: NSW, VIC, QLD, SA, WA, TAS, NT, ACT
- **Major Councils**: Sydney, Melbourne, Brisbane, Perth, Adelaide
- **Specialized Agencies**: Transport, environment, mining, agriculture

### 🔍 Easy Discovery
- Organized by jurisdiction and service type
- Search functionality across all services
- Standardized metadata for all entries
- Regular verification and status monitoring

## 🚀 Quick Start

### Find Services by State
```
portals/state-territory/
├── nsw/           # New South Wales services
├── vic/           # Victoria services  
├── qld/           # Queensland services
├── sa/            # South Australia services
├── wa/            # Western Australia services
├── tas/           # Tasmania services
├── nt/            # Northern Territory services
└── act/           # ACT services
```

### Find Services by Type
```
services/
├── rest-services/     # ArcGIS REST and similar APIs
├── wms-wfs/          # OGC web mapping services
├── apis/             # REST APIs and GraphQL
└── download-services/ # Bulk download and FTP
```

### Interactive Web Maps
```
tools/web-applications/
├── mapping-viewers.md    # General mapping applications
├── analysis-tools.md     # Spatial analysis tools
└── mobile-apps.md       # Mobile applications
```

## 📊 Featured Services

### 🌏 National Services
- **[NationalMap](https://nationalmap.gov.au/)** - Australia's primary national mapping platform
- **[Data.gov.au](https://data.gov.au/)** - Australian Government's open data portal
- **[Geoscience Australia](https://www.ga.gov.au/)** - National geoscience data and services

### 🗺️ State Mapping Platforms
- **NSW**: [NSW Spatial Collaboration Portal](https://portal.spatial.nsw.gov.au/portal/)
- **VIC**: [Vicmap Viewer](https://mapshare.vic.gov.au/vicmapviewer/)
- **QLD**: [Queensland Globe](https://qldglobe.information.qld.gov.au/)
- **SA**: [Location SA Map Viewer](https://location.sa.gov.au/viewer/)
- **WA**: [SLIP Map Viewer](https://maps.slip.wa.gov.au/landgate/)
- **TAS**: [The LIST Map](https://maps.thelist.tas.gov.au/listmap/app/list/map)
- **NT**: [NR Maps](https://nrmaps.nt.gov.au/nrmaps.html)
- **ACT**: [ACTmapi](https://www.actmapi.act.gov.au/)

### 🔗 REST Service Endpoints
- **NSW**: [maps.six.nsw.gov.au](https://maps.six.nsw.gov.au/arcgis/rest/services/public)
- **QLD**: [spatial-gis.information.qld.gov.au](https://spatial-gis.information.qld.gov.au/arcgis/rest/services)
- **SA**: [location.sa.gov.au](https://location.sa.gov.au/server6/rest/services)
- **WA**: [services.slip.wa.gov.au](https://services.slip.wa.gov.au/public/rest/services)

## 💻 Usage Examples

### Access a WMS Service in Python
```python
import requests
from owslib.wms import WebMapService

# Connect to NSW WMS service
wms = WebMapService('https://maps.six.nsw.gov.au/arcgis/services/public/NSW_Base_Map/MapServer/WMSServer')

# List available layers
print(list(wms.contents.keys()))

# Get map image
img = wms.getmap(
    layers=['0'],
    srs='EPSG:4326',
    bbox=(150.0, -34.0, 151.0, -33.0),
    size=(512, 512),
    format='image/png'
)
```

### Load Services in QGIS
```python
# Add ArcGIS REST service as layer
layer_url = "https://services.slip.wa.gov.au/public/rest/services/SLIP_Public_Services/Transport/MapServer"
layer = QgsRasterLayer(f"url={layer_url}", "WA Transport", "arcgismapserver")
QgsProject.instance().addMapLayer(layer)
```

### JavaScript Web Map
```javascript
// Using Leaflet with Australian services
var map = L.map('map').setView([-25.2744, 133.7751], 4);

// Add NSW base map
L.tileLayer('https://maps.six.nsw.gov.au/arcgis/rest/services/public/NSW_Base_Map/MapServer/tile/{z}/{y}/{x}', {
    attribution: 'NSW Spatial Services'
}).addTo(map);
```

## 📁 Repository Structure

```
National_Spatial_Data/
├── portals/                    # Data portals and catalogs
│   ├── federal/               # Commonwealth government
│   ├── state-territory/       # State and territory services
│   ├── local-government/      # Council and regional services
│   └── specialized/           # Sector-specific portals
├── services/                  # Web services and APIs
│   ├── rest-services/         # ArcGIS REST and similar
│   ├── wms-wfs/              # OGC standards services
│   ├── apis/                 # REST APIs and GraphQL
│   └── download-services/     # Bulk download services
├── tools/                     # Applications and utilities
│   ├── web-applications/      # Web-based tools
│   ├── desktop-tools/         # Desktop software
│   └── scripts/              # Automation scripts
├── examples/                  # Code examples and tutorials
│   ├── javascript/           # Web development examples
│   ├── python/               # Python integration
│   ├── r/                    # R programming examples
│   └── qgis/                 # QGIS integration
└── docs/                     # Documentation
    ├── usage-guide.md        # How to use services
    ├── api-reference.md      # API documentation
    └── troubleshooting.md    # Common issues
```

## 🔄 Service Monitoring

### Health Status
We monitor all listed services for:
- **Availability**: Service uptime and response
- **Performance**: Response times and reliability
- **Changes**: Updates to endpoints or metadata
- **Issues**: Broken links or service problems

### Status Dashboard
- 🟢 **Active**: Service operational and verified
- 🟡 **Warning**: Service slow or intermittent issues
- 🔴 **Down**: Service unavailable or broken
- 🔵 **Maintenance**: Scheduled maintenance period

## 📖 Documentation

- **[Usage Guide](docs/usage-guide.md)**: How to connect to and use services
- **[API Reference](docs/api-reference.md)**: Technical documentation for APIs
- **[Service Status](docs/service-status.md)**: Current status of all monitored services
- **[Troubleshooting](docs/troubleshooting.md)**: Common issues and solutions

## 🤝 Contributing

We welcome contributions from the spatial data community!

### How to Contribute
- **Add New Services**: Submit new spatial services and portals
- **Update Information**: Keep service details current
- **Report Issues**: Flag broken links or outdated information
- **Improve Documentation**: Enhance guides and examples

### Contribution Process
1. Fork the repository
2. Add/update service information using our templates
3. Test all links and services
4. Submit a pull request with detailed description

See our [Contributing Guidelines](CONTRIBUTING.md) for detailed instructions.

## 📊 Service Statistics

| Category | Count | Last Updated |
|----------|-------|--------------|
| Data Portals | 180+ | 2024-06-21 |
| REST Services | 250+ | 2024-06-21 |
| WMS/WFS Services | 150+ | 2024-06-21 |
| Web Applications | 120+ | 2024-06-21 |
| APIs | 80+ | 2024-06-21 |

## 🌐 API Access

### REST API Endpoints
- **Services Catalog**: `https://api.spatialdirectory.au/v1/services`
- **Health Status**: `https://api.spatialdirectory.au/v1/status`
- **Search**: `https://api.spatialdirectory.au/v1/search?q={query}`

### Export Formats
- **JSON**: Machine-readable service catalogs
- **CSV**: Spreadsheet-compatible listings
- **GeoJSON**: Services with geographic coverage
- **RSS**: Updates feed for new services

## 📜 Licensing

- **Repository Content**: [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)
- **Individual Services**: Each service maintains its own licensing terms
- **Code Examples**: MIT License

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/Orthopyroxene/National_Spatial_Data/issues)
- **Discussions**: [GitHub Discussions](https://github.com/Orthopyroxene/National_Spatial_Data/discussions)
- **Email**: spatial-directory@example.com

## 🏆 Acknowledgments

Thanks to:
- Australian government agencies providing open spatial services
- State and territory spatial data teams
- The Australian spatial data community
- Contributors maintaining this directory

---

**Disclaimer**: This directory is community-maintained and not officially affiliated with any government agency. Service availability and accuracy may vary. Always verify with original sources for critical applications.

**Last Updated**: June 21, 2024 | **Services Monitored**: 450+ | **Contributors**: 25+