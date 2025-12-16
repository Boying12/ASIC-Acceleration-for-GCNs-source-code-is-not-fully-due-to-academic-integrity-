# ASIC Acceleration for Graph Convolutional Networks (GCNs)

## Overview
- Designed a low-power ASIC accelerator for Graph Convolutional Neural Networks (GCNs)
- Targeted node classification on graph-structured data
- Completed a full ASIC design flow from RTL to post-layout analysis

## GCN Computation
- Feature Aggregation  
  - Aggregates neighboring node features based on graph connectivity  
  - Exploits sparse graph structure to reduce computation overhead
- Feature Transformation  
  - Performs matrix multiplication with a weight matrix for dimensionality reduction
- Classification  
  - Uses an argmax operation to determine the final class for each node

## Key Design Techniques
- Sparse COO (Coordinate) format for adjacency representation  
  - Avoids dense adjacency matrix storage  
  - Reduces memory usage and unnecessary multiplications
- Hardware-efficient aggregation  
  - Uses accumulation-based logic instead of full matrix multiplication
- Parametrized architecture  
  - Supports design-space exploration for latency and power trade-offs
- Boundary-registered design  
  - All inputs and outputs are registered to improve timing closure

## ASIC Flow
- RTL Design  
  - Implemented the GCN module in Verilog
- Logic Synthesis  
  - Synthesized using Synopsys Design Compiler
  - Verified functional correctness with post-synthesis simulation
- Automatic Place-and-Route (APR)  
  - Performed using Cadence Innovus
  - Included clock tree synthesis and layout optimization
- Post-Layout Analysis  
  - Conducted post-APR simulation
  - Performed VCD-based power analysis in Innovus

## Results
- End-to-end latency: < 100 ns
- Functional correctness verified at:
  - RTL level
  - Post-synthesis level
  - Post-APR level
- Power optimized under strict timing constraints

## Repository Structure
- `Synthesis/` – Design Compiler scripts and reports
- `Innovus/` – APR scripts, layout results, and power reports
- `LAB4_Report.pdf` – Detailed design report and analysis
