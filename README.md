<div align="center">
  <h1>🌱 Agro VI: Smart Farming Assistant</h1>
  <p><strong>Solar-powered, zero-cloud Edge AI delivering real-time crop diagnostics and precision irrigation directly to the field.</strong></p>
  <p><i>Smart India Hackathon 2026 — Problem Statement 26180</i></p>
</div>

---

## 🚀 Quick Links for Evaluators
> **Note to Evaluators:** Click the links below to view our project demonstration and technical documentation.
- [🎥 **Video Demonstration**](#) *(Insert YouTube/Drive link here)*
- [📄 **Technical Project Report (PDF)**](#) *(Insert file link here)*
- [📊 **SIH Presentation Deck**](#) *(Insert file link here)*

---

## ⚠️ The Problem: Rural Bottlenecks in Agriculture
Farmers face massive crop losses and shrinking profit margins due to delayed disease detection and inefficient resource management. 
* **The Connectivity Gap:** Cloud-based ag-tech fails in rural areas due to patchy or non-existent internet coverage, rendering real-time smartphone apps useless.
* **The Literacy Barrier:** Complex dashboards and text-heavy apps exclude farmers who lack technical literacy.
* **Resource Waste:** Manual, timer-based flooding wastes massive amounts of groundwater and washes away expensive fertilizers, while blanket pesticide spraying destroys soil health and cuts into profits.

---

## 💡 Our Solution: Key Features
Agro VI processes everything locally on the device, bringing precision agriculture to any farm regardless of network availability.

1. **Edge-Based Vision Diagnostics:** Classifies fungal and bacterial diseases as well as nutrient deficiencies by running quantized INT8 models directly on the device, within 200 milliseconds[cite: 3].
2. **Micro-Pest Triage:** The micro-pest sticky trap counter employs low-power macro imaging in order to count and classify harmful insects before a swarm situation develops[cite: 3].
3. **Evapotranspiration Irrigation:** The FAO-56 Penman-Monteith method is used to combine soil moisture and microclimate data in order to automate the operation of the pumps and prevent water stress[cite: 3].
4. **Predictive Climate Risk Warning:** Forecasts the rapid development of blight by monitoring levels of humidity that are sustained above 85% and temperature increases that occur 48 hours prior to the appearance of visible symptoms[cite: 3].

---

## ⚙️ System Architecture Flow

```mermaid
graph TD
    classDef main fill:#065f46,stroke:#fff,stroke-width:2px,color:#fff;
    classDef sub fill:#10b981,stroke:#fff,stroke-width:1px,color:#fff;
    classDef action fill:#d97706,stroke:#fff,stroke-width:1px,color:#fff;
    classDef output fill:#047857,stroke:#fff,stroke-width:1px,color:#fff;

    A[Multi-Sensor Data Capture]:::main --> B{On-Device Edge Processing}:::main
    
    B --> C(Quantized Vision Models):::sub
    B --> D(FAO-56 Thermodynamic Math):::sub
    
    C --> E[Autonomous Decision Logic]:::main
    D --> E
    
    E -->|Soil Deficit Detected| F(Trigger Pump Relay):::action
    E -->|Blight Risk / Pest Threshold| G(Generate Treatment Advice):::action
    
    F --> H{Field Output & Farmer Advisory}:::main
    G --> H
    
    H --> I[Onboard Voice Advisory]:::output
    H --> J[Color-Coded Status Flags]:::output
    H --> K[Offline LoRa/BLE Smartphone Sync]:::output
