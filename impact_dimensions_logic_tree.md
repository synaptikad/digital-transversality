# Logical Tree of Impact Dimensions with Multi-Level Indicators

## General Structure of Impact Dimensions

```
IMPACTS (4 main dimensions)
├── ECONOMIC (temporalized financial flows)
├── ENVIRONMENTAL (impact on the living world)
├── SOCIAL (impact on human collective)
└── GENERATIVE (impact on fundamental values)
```

## 1. ECONOMIC IMPACTS (temporalized)

### Hierarchical Structure
```
ECONOMIC
├── CAPEX (Capital Expenditure - initial investment)
│   ├── Study and design costs
│   ├── Implementation/adaptation costs
│   └── Commissioning costs
├── OPEX (Operational Expenditure - operation)
│   ├── Energy consumption
│   ├── Maintenance and upkeep
│   ├── Management and operation
│   └── Insurance and taxes
└── FINEX (Final Expenditure - end of life)
    ├── Dismantling/deconstruction
    ├── Recovery/recycling
    └── Site restoration
```

### Multi-Level Indicators

#### Level 1 - Traditional Financial Stakeholder
- **Simple ROI**: Traditional return on investment
- **Payback**: Investment payback period
- **NPV**: Net present value over lifetime

#### Level 2 - Extended Financial Stakeholder
- **Extended TCO**: Total cost including quantifiable externalities
- **Societal ROI**: Including productivity gains, public health
- **Optimized residual value**: Including reuse potential

#### Level 3 - Systemic Vision
- **Systemic avoided cost**: Savings induced on the entire system
- **Option value**: Future adaptation capacity
- **Commons impact**: Contribution to shared goods

## 2. ENVIRONMENTAL IMPACTS (living world)

### Hierarchical Structure
```
ENVIRONMENTAL
├── CLIMATE (climatic balances)
│   ├── Direct GHG emissions
│   ├── Carbon sequestration
│   └── Climate resilience
├── RESOURCES (biosphere withdrawals)
│   ├── Raw materials
│   ├── Primary energy
│   └── Water
├── BIODIVERSITY (diversity of life)
│   ├── Natural habitats
│   ├── Ecological corridors
│   └── Local species
└── POLLUTION (environmental alterations)
    ├── Air (particles, VOCs, etc.)
    ├── Water (discharge, runoff)
    └── Soil (contamination, impermeabilization)
```

### Multi-Level Indicators

#### Level 1 - Regulatory Compliance
- **Regulatory CO₂ emissions**: According to current RT/RE standards
- **Energy consumption**: kWh/m²/year
- **Recycling rate**: % recycled materials

#### Level 2 - Environmental Performance
- **Differential LCA**: Impact vs reference scenario
- **Ecological footprint**: Equivalent surfaces consumed
- **Biodiversity balance**: Habitat gain/loss

#### Level 3 - Ecological Regeneration
- **Regeneration capacity**: Positive contribution to ecosystems
- **Ecosystem resilience**: Strengthening environmental stability
- **Biomimicry**: Degree of inspiration/integration of natural processes

## 3. SOCIAL IMPACTS (human collective)

### Hierarchical Structure
```
SOCIAL
├── PUBLIC HEALTH (collective physical well-being)
│   ├── Indoor/outdoor air quality
│   ├── Thermal and acoustic comfort
│   └── Safety and accident prevention
├── SOCIAL COHESION (bonds and interactions)
│   ├── Meeting and sharing spaces
│   ├── Social and generational diversity
│   └── Participatory governance
├── EQUITY (justice and accessibility)
│   ├── Universal accessibility
│   ├── Equal access to services
│   └── Inequality reduction
└── CULTURE (transmission and creativity)
    ├── Heritage and memory
    ├── Learning spaces
    └── Artistic and creative expression
```

### Multi-Level Indicators

#### Level 1 - Social Compliance
- **Accessibility rate**: % accessible spaces for disabled persons
- **User satisfaction**: Standardized surveys
- **Occupancy rate**: Effective use of spaces

#### Level 2 - Social Dynamics
- **Diversity index**: Diversity of populations welcomed
- **Interaction frequency**: Measurement of social exchanges
- **Collective appropriation**: Degree of user investment

#### Level 3 - Social Transformation
- **Commons emergence**: Creation of shared goods
- **Social innovation**: New collective practices
- **Community resilience**: Collective adaptation capacity

## 4. GENERATIVE IMPACTS (on the 8 fundamental values)

### Hierarchical Structure
```
GENERATIVE
├── HEALTH (physical and mental)
│   ├── Physical vitality
│   ├── Mental balance
│   └── Psychological fulfillment
├── PEACE (in all its forms)
│   ├── Personal serenity
│   ├── Social harmony
│   ├── Ecological balance
│   └── Geopolitical stability
├── TRUST (security and reliability)
│   ├── Physical security
│   ├── Technical reliability
│   └── Social predictability
├── FRIENDSHIP (authentic bonds)
│   ├── Quality of relationships
│   ├── Mutual aid
│   └── Sense of belonging
├── KNOWLEDGE (learning and meaning)
│   ├── Knowledge acquisition
│   ├── Creativity and innovation
│   └── Search for meaning
├── FREEDOM (autonomy and dignity)
│   ├── Freedom of choice
│   ├── Autonomy of action
│   └── Respected dignity
├── BEAUTY (aesthetics and harmony)
│   ├── Harmony of forms
│   ├── Spiritual elevation
│   └── Creative inspiration
└── JUSTICE (equity and solidarity)
    ├── Equal opportunities
    ├── Active solidarity
    └── Imbalance repair
```

### Multi-Level Indicators

#### Level 1 - Objective Measures
- **Biomarkers**: Cortisol, heart rate variability (health)
- **Cognitive tests**: Attention, creativity (knowledge)
- **Behavioral observations**: Interactions, appropriation (friendship)

#### Level 2 - Subjective Evaluations
- **Well-being scales**: Scientifically validated questionnaires
- **Life stories**: Qualitative impact testimonies
- **Self-assessment**: Personal perception of changes

#### Level 3 - Systemic Emergences
- **Social innovations**: New practices generated
- **Contagion effects**: Spread of positive practices
- **Cultural transformation**: Evolution of collective values

## Compilation and Aggregation Methods

### Weighting Algorithms
```python
def calculate_global_impact(measured_impacts, stakeholder_profile):
    """
    Compiles impacts according to stakeholder profile
    """
    weights = get_weights(stakeholder_profile)
    
    economic_impact = sum(measured_impacts.economic * weights.eco)
    environmental_impact = sum(measured_impacts.environmental * weights.env)
    social_impact = sum(measured_impacts.social * weights.soc)
    generative_impact = sum(measured_impacts.generative * weights.gen)
    
    return {
        'global_score': weighted_average([
            economic_impact, environmental_impact, 
            social_impact, generative_impact
        ], weights.dimensions),
        'detail_by_dimension': {
            'economic': economic_impact,
            'environmental': environmental_impact,
            'social': social_impact,
            'generative': generative_impact
        }
    }
```

### Typical Weighting Profiles

#### "Traditional Investor" Profile
```json
{
    "economic": 0.70,
    "environmental": 0.15,
    "social": 0.10,
    "generative": 0.05
}
```

#### "Public Authority" Profile
```json
{
    "economic": 0.25,
    "environmental": 0.25,
    "social": 0.30,
    "generative": 0.20
}
```

#### "Systemic Vision" Profile
```json
{
    "economic": 0.15,
    "environmental": 0.25,
    "social": 0.25,
    "generative": 0.35
}
```

## Temporal Compilation Levels

### Short Term (0-2 years)
- Immediate implementation impacts
- Temporary disruptions
- First usage feedback

### Medium Term (2-10 years)
- Performance stabilization
- Emergence of social dynamics
- Progressive optimization

### Long Term (10+ years)
- Impacts on fundamental values
- Cultural transformations
- Resilience and adaptability

This logical tree allows for precise modeling of all impacts while offering different reading levels according to the maturity and interests of stakeholders.