# ATOM

## Structure
```
atomg/
├── CMakeLists.txt
├── README.md
├── include/
│   └── atomg/
│       ├── data/
│       │   ├── dataset.hpp        # Dataset management and loading
│       │   ├── vector.hpp         # Vector data structure
│       │   └── distance.hpp       # Distance computation
│       │
│       ├── index/
│       │   ├── atomg.hpp          # Main ATOMG index
│       │   ├── parameters.hpp     # Index configuration
│       │   ├── builder.hpp        # Index construction
│       │   ├── searcher.hpp       # Search implementation
│       │   └── maintainer.hpp     # Dynamic maintenance
│       │
│       └── io/
│           ├── loader.hpp         # FVECS/IVECS file loader
│           └── serializer.hpp     # Index serialization
│
└── src/
    └── main.cpp                   # Example usage & implementation

```

## Requirements
- C++11 


## Build
```bash
mkdir -p build && cd build
cmake ..
make -j
```

## Usage

```
./atomg static /path/to/base.fvecs /path/to/query.fvecs /path/to/groundtruth.ivecs max_degree num_layers  --save index.bin
```

```
./atomg dynamic /path/to/index.bin /path/to/updates.dat /path/to/query.fvecs /path/to/groundtruth.ivecs  --save updated_index.bin
```

### Data Format
- Base vectors: `xxx_base.fvecs`
- Query vectors: `xxx_query.fvecs` 
- Ground truth: `xxx_groundtruth.ivecs`
