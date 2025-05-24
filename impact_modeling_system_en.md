# Explanatory Guide - Impact Modeling System for Digital Transversality

## Table of Contents
1. [Overview](#overview)
2. [Philosophy and Principles](#philosophy-and-principles) 
3. [Tree Structure](#tree-structure)
4. [Modeling Methodology](#modeling-methodology)
5. [Managing Interdependencies](#managing-interdependencies)
6. [Critical Threshold System](#critical-threshold-system)
7. [Scalability and Learning](#scalability-and-learning)
8. [Granularity Adaptation](#granularity-adaptation)
9. [Practical Use Cases](#practical-use-cases)
10. [Implementation Guide](#implementation-guide)

---

## Overview

### System Objective
This modeling system enables **evaluation and optimization of the real impact** of development projects (building, district, territory) on what truly matters: sustainable human flourishing and regeneration of living systems.

### Fundamental Principle
> "Designing living environments should not be limited to organizing functional or profitable spaces. It's about creating environments capable of supporting genuine sustainable human flourishing."

### Key Innovation
The system reveals and quantifies the **hidden links** between technical choices and fundamental values, enabling informed decisions that simultaneously optimize economic performance and collective well-being.

---

## Philosophy and Principles

### True Values
Beyond money (a simple social convention), universally shared values are:
- **Health** (physical and mental)
- **Peace** (serenity, harmony, absence of war)
- **Trust** (security, reliability, predictability)
- **Friendship** (social bonds, cooperation, solidarity)
- **Knowledge** (learning, creativity, meaning)
- **Freedom** (autonomy, dignity, choice)
- **Beauty** (aesthetics, harmony, inspiration)
- **Justice** (equity, equality, reparation)

### Economic Reality Principle
Money has value only through its **promise of energy or matter flows**. The system therefore integrates financial constraints while placing them in their proper proportion: means, not an end.

### Multi-level Approach
The system offers **different levels of reading** according to stakeholder maturity, allowing to "speak the language" of each while keeping focus on true values.

---

## Tree Structure

### The 4 Main Dimensions

```
IMPACTS
├── ECONOMIC (temporalized financial flows)
├── ENVIRONMENTAL (impact on the living world)  
├── SOCIAL (impact on the human collective)
└── GENERATIVE (impact on the 8 fundamental values)
```

### Why This Structure?

#### 1. ECONOMIC IMPACTS
- **Temporalized**: CAPEX / OPEX / FINEX for a lifecycle vision
- **Objective**: Speak to financial decision-makers in their language
- **Innovation**: Quantification of co-benefits (health → productivity → savings)

#### 2. ENVIRONMENTAL IMPACTS  
- **Living approach**: Beyond CO₂, impact on biodiversity, ecosystems
- **Objective**: Measure regeneration vs degradation of the natural world
- **Innovation**: Positive contribution indicators (not just "less bad")

#### 3. SOCIAL IMPACTS
- **Human collective**: Public health, cohesion, equity, culture
- **Objective**: Measure the quality of "living together" 
- **Innovation**: Metrics for emergence of positive collective dynamics

#### 4. GENERATIVE IMPACTS
- **The 8 values**: Direct impact on what nourishes human flourishing
- **Objective**: Reveal the "invisible" impact of technical choices on well-being
- **Innovation**: Quantification of previously intuitive concepts

---

## Modeling Methodology

### 3-Layer Approach

#### Layer 1 - Objective Measures
```python
# Example: Impact of lighting system on health
{
    "measure": "salivary_cortisol_concentration",
    "unit": "ng/mL", 
    "value_before": 12.5,
    "value_after": 8.3,
    "improvement": 33.6,
    "confidence": 0.8
}
```

#### Layer 2 - Subjective Evaluations  
```python
# Example: Well-being perception
{
    "scale": "WHO5_wellbeing",
    "sample": 150,
    "score_before": 6.2,
    "score_after": 8.1, 
    "significance": 0.001
}
```

#### Layer 3 - Systemic Emergences
```python  
# Example: Spontaneous social innovations
{
    "observation": "spontaneous_community_gardens_creation",
    "frequency": "3_initiatives_in_6_months",
    "impact": "measured_social_cohesion",
    "type": "unplanned_emergence"
}
```

### Multi-criteria Compilation

The central algorithm compiles all impacts according to contextual **weighting profiles**:

```python
def calculate_global_impact(measures, stakeholder_profile, project_context):
    """
    Calculate global impact according to stakeholder profile
    """
    weightings = get_weightings(stakeholder_profile, project_context)
    
    # Compilation by dimension
    eco = compile_economic_impacts(measures.economic, weightings.eco)
    env = compile_environmental_impacts(measures.environmental, weightings.env) 
    soc = compile_social_impacts(measures.social, weightings.soc)
    gen = compile_generative_impacts(measures.generative, weightings.gen)
    
    # Account for interdependencies
    interdependencies = calculate_correlations(eco, env, soc, gen)
    
    return {
        'global_score': weighted_average([eco, env, soc, gen], weightings.dimensions) + interdependencies,
        'detail': {
            'economic': eco,
            'environmental': env, 
            'social': soc,
            'generative': gen,
            'synergies': interdependencies
        }
    }
```

---

## Managing Interdependencies

### Co-benefits Principle
Each improvement in one dimension can **generate benefits in other dimensions**. The system quantifies these often-ignored synergies.

### Dynamic Correlation Matrix

```python
# Data structure for correlations
correlations = {
    "physical_health → productivity → economic": {
        "coefficient": 0.32,  # 1% health improvement = 0.32% productivity gain
        "activation_delay": 3,  # months to see effect  
        "effect_duration": 24,  # months of persistence
        "confidence": 0.75,  # level of scientific certainty
        "sources": [
            "harvard_productivity_study_2019",
            "google_office_experience_feedback"
        ],
        "application_context": ["offices", "collaborative_spaces"]
    },
    
    "social_cohesion → security → economic": {
        "coefficient": 0.18,  # weaker but measurable effect
        "activation_delay": 12,  # longer for social cohesion
        "effect_duration": 60,  # more durable effect
        "confidence": 0.60,  # less data, more qualitative
        "mechanism": "Improved cohesion → Reduced incivilities → Lower security/maintenance costs"
    }
}
```

### Synergy Calculation

```python
def calculate_synergies(primary_impacts):
    """
    Calculate synergy effects between dimensions
    """
    synergies = 0
    
    for correlation in correlations:
        if correlation.conditions_met(primary_impacts):
            primary_effect = primary_impacts[correlation.source_dimension]
            secondary_effect = primary_effect * correlation.coefficient * correlation.confidence
            
            # Apply delay and duration
            temporalized_effect = apply_temporality(secondary_effect, correlation.delay, correlation.duration)
            
            synergies += temporalized_effect
            
    return synergies
```

### Concrete Synergy Examples

#### Air Quality Improvement → Impact Cascade
1. **Direct**: Reduction in respiratory problems (-15% medical consultations)
2. **Mental Health**: Improved cognitive abilities (+12% intellectual performance) 
3. **Social**: Reduced absenteeism (+8% workplace attendance)
4. **Economic**: Productivity gains (+€180k/year for 200 people)
5. **Generative**: Improved trust in work environment

#### Green Space Creation → Multiple Effects
1. **Environmental**: Carbon sequestration, biodiversity, thermal regulation
2. **Health**: Stress reduction, improved air, physical activity
3. **Social**: Meeting spaces, collective pride, appropriation  
4. **Economic**: Real estate valorization, reduced air conditioning costs
5. **Generative**: Connection to living systems, beauty, peace

---

## Critical Threshold System

### "Red Line" Philosophy
Certain impacts must never fall below **minimum thresholds**, even if other dimensions are excellent.

### Threshold Typology

#### Regulatory Thresholds (absolute)
```python
regulatory_thresholds = {
    "public_health": {
        "indoor_CO2": {"max": 1000, "unit": "ppm", "source": "decree_2012"},
        "ambient_noise": {"max": 35, "unit": "dB(A)", "source": "WHO_2018"}
    },
    "safety": {
        "fire_resistance": {"min": "REI_60", "source": "construction_code"},
        "exit_width": {"min": 0.9, "unit": "m", "source": "ERP_2022"}
    },
    "environment": {
        "energy_performance": {"min_class": "C", "source": "RE2020"}
    }
}
```

#### Ethical Thresholds (contextual)
```python
ethical_thresholds = {
    "equity": {
        "disabled_accessibility": {"min": 80, "unit": "%", "context": "public_buildings"},
        "social_diversity": {"min": 0.3, "unit": "shannon_index", "context": "social_housing"}
    },
    "dignity": {
        "minimum_surface": {"min": 9, "unit": "m²/person", "context": "housing"},
        "natural_light_access": {"min": 2, "unit": "%_daylight_factor"}
    }
}
```

#### Generative Thresholds (evolving)
```python
generative_thresholds = {
    "mental_health": {
        "chronic_stress": {"max": 0.7, "unit": "normalized_cortisol_index"},
        "environment_satisfaction": {"min": 6, "unit": "scale_1_10"}
    },
    "social_cohesion": {
        "social_isolation": {"max": 0.2, "unit": "proportion_isolated"},
        "neighborhood_conflicts": {"max": 0.1, "unit": "incidents_per_month"}
    }
}
```

### Alert and Compensation Mechanism

```python
def check_thresholds(calculated_impacts, project_context):
    """
    Check thresholds and propose compensations if necessary
    """
    alerts = []
    compensations = []
    
    for dimension, thresholds in get_applicable_thresholds(project_context):
        for criterion, threshold_value in thresholds.items():
            calculated_value = calculated_impacts[dimension][criterion]
            
            if violates_threshold(calculated_value, threshold_value):
                alert = {
                    "type": "critical_threshold",
                    "dimension": dimension,
                    "criterion": criterion,
                    "current_value": calculated_value,
                    "required_value": threshold_value,
                    "gap": calculate_gap(calculated_value, threshold_value)
                }
                alerts.append(alert)
                
                # Propose compensations
                compensations.extend(propose_compensations(alert, project_context))
    
    return {
        "alerts": alerts,
        "possible_compensations": compensations,
        "project_acceptable": len([a for a in alerts if a.type == "critical"]) == 0
    }
```

---

## Scalability and Learning

### Hybrid Learning Architecture

The system evolves through **3 complementary mechanisms**:

#### 1. Regulatory Evolution (automatic)
```python
class RegulatoryUpdate:
    def __init__(self):
        self.monitoring_sources = [
            "official_journal_API",
            "EUR_lex_API", 
            "ADEME_data",
            "WHO_guidelines"
        ]
    
    def check_updates(self):
        """Check daily for new regulations"""
        for source in self.monitoring_sources:
            new_rules = source.get_updates()
            if new_rules:
                self.automatically_integrate(new_rules)
                self.notify_administrators(new_rules)
```

#### 2. Experience Feedback Learning (semi-automatic)
```python
class ExperienceFeedbackLearning:
    def analyze_completed_project(self, project):
        """
        Analyze a completed project to improve predictions
        """
        gaps = calculate_prediction_reality_gaps(project)
        
        if gaps.significant():
            # Model adjustment proposal
            proposed_adjustments = {
                "correlations_to_modify": analyze_correlations(gaps),
                "coefficients_to_adjust": calculate_new_coefficients(gaps),
                "new_synergies_detected": detect_emergences(project)
            }
            
            # Human validation required before integration
            return submit_expert_validation(proposed_adjustments)
```

#### 3. Societal Evolution (manual)
```python
class SocietalEvolution:
    def __init__(self):
        self.ethics_committee = [
            "environmental_philosopher",
            "urban_sociologist", 
            "citizen_representative",
            "public_health_expert",
            "ecological_economist"
        ]
    
    def annual_values_review(self):
        """
        Democratic review of value weightings
        """
        citizen_survey = conduct_societal_values_survey()
        trend_analysis = analyze_societal_values_evolution()
        
        evolution_proposal = self.ethics_committee.deliberate(
            citizen_survey, 
            trend_analysis
        )
        
        if consensus_reached(evolution_proposal):
            return integrate_new_weightings(evolution_proposal)
```

### Evolution Traceability
```python
# Each modification is traced
modification_log = {
    "timestamp": "2024-03-15T14:30:00Z",
    "type": "correlation_adjustment",
    "source_dimension": "mental_health",
    "target_dimension": "economic_productivity", 
    "old_coefficient": 0.25,
    "new_coefficient": 0.32,
    "justification": "Consolidation of data from 15 completed projects",
    "validated_by": "scientific_committee",
    "estimated_impact": "12%_improvement_in_prediction_accuracy"
}
```

---

## Granularity Adaptation

### Proportionality Principle
Measurement precision adapts to **available resources** and **project stakes**.

### Adaptation Matrix

#### By Project Scale

| Scale | Number of Indicators | Main Focus | Example |
|-------|---------------------|------------|---------|
| Building < 1000m² | 20 essential indicators | Occupant comfort | Individual house renovation |
| Building 1000-5000m² | 50 balanced indicators | Performance + well-being | Office building |
| District 5000-50000m² | 100 complete indicators | Social dynamics | Eco-district |
| Territory > 50000m² | 200+ exhaustive indicators | Systemic transformation | Urban planning |

#### By Project Phase

```python
indicators_by_phase = {
    "intention": {
        "type": "prospective",
        "precision": "orders_of_magnitude",
        "method": "similar_project_analogies",
        "example": "Estimated CO₂ reduction: 30-50%"
    },
    
    "design": {
        "type": "simulated", 
        "precision": "fine_modeling",
        "method": "specialized_software",
        "example": "Simulated CO₂ reduction: 42% ±5%"
    },
    
    "construction": {
        "type": "measured",
        "precision": "real_time_sensors", 
        "method": "dedicated_instrumentation",
        "example": "Measured CO₂ reduction: 38% (first 6 months)"
    },
    
    "operation": {
        "type": "consolidated",
        "precision": "long_term_usage_feedback",
        "method": "multi_year_monitoring",
        "example": "Confirmed CO₂ reduction: 41% (3-year average)"
    }
}
```

#### By Available Budget

```python
def adapt_granularity_budget(available_budget, project_scale):
    """
    Adapt measurement granularity according to budget
    """
    budget_per_m² = available_budget / project_scale.surface
    
    if budget_per_m² < 5:  # Tight budget
        return {
            "indicators": get_essential_indicators(),
            "methods": ["simple_surveys", "spot_measurements"],  
            "frequency": "annual"
        }
    
    elif budget_per_m² < 15:  # Standard budget
        return {
            "indicators": get_balanced_indicators(),
            "methods": ["basic_sensors", "regular_surveys"],
            "frequency": "quarterly" 
        }
    
    else:  # Comfortable budget
        return {
            "indicators": get_exhaustive_indicators(),
            "methods": ["advanced_sensors", "in_depth_studies"],
            "frequency": "continuous"
        }
```

---

## Practical Use Cases

### Case 1 - Energy Renovation of Office Building

#### Context
- Surface: 3000 m²
- Budget: €400k
- Stakeholder: Traditional investor (ROI focus)

#### System Application

**Level 1 - Investor language**:
```
Traditional ROI: 4.2 years
Energy savings: €45k/year  
Asset valorization: +€180k
```

**Co-benefits revelation**:
```
Air quality improvement → +12% productivity → €85k/year indirect savings
Real ROI including co-benefits: 2.8 years
```

**Progression toward expanded vision**:
```
Health impact: 35% reduction in respiratory problems
Social impact: +23% job satisfaction  
Generative impact: Overall well-being improvement 8.1/10
```

### Case 2 - Public Space Development in District

#### Context  
- Surface: 15000 m²
- Budget: €2M
- Stakeholder: Public authority (multi-criteria)

#### System Application

**Economic impacts**:
```
CAPEX: €2M development
OPEX: -€15k/year (maintenance savings through green spaces)
District property valorization: +€5M over 10 years
```

**Environmental impacts**:
```
Carbon sequestration: +120 tons CO₂/year
Biodiversity: +40% local species
Thermal regulation: -3°C summer temperatures
```

**Social impacts**:
```
Public space usage: +180%
Local job creation: 25 direct/indirect jobs
Insecurity feeling reduction: -45%
```

**Generative impacts**:
```
Health: +25% residents' physical activity
Peace: -38% neighborhood conflicts  
Friendship: +60% spontaneous social interactions
Beauty: Aesthetic satisfaction 9.2/10
```

### Case 3 - Eco-district Construction  

#### Context
- Surface: 80000 m²
- Budget: €50M  
- Stakeholder: Systemic vision (societal transformation)

#### Complete System Application

**Complex modeling**:
- 150+ indicators
- Correlations between 12 sub-systems
- 50-year simulation
- Integration of 8 fundamental values

**Synthetic results**:
```
Global flourishing score: 8.7/10
Net regenerative impact: +45% vs initial situation
Social innovation: 12 emerging new practices
Climate resilience: 80% autonomy in essential resources
```

---

## Integration into Digital Transversality Ecosystem

This impact tree integrates into the global Digital Transversality approach:

### Link with Main Document
This impact system enriches the [Digital Transversality methodology for existing building adaptation](https://github.com/synaptikad/digital-transversality/blob/main/transversalite-digitale-adaptation.md) by bringing a quantitative dimension to qualitative evaluations.

### Link with Databases
The indicators defined here feed the [code databases](https://github.com/synaptikad/de-code-/blob/main/README.md) that allow the inference engine to automatically calculate the impacts of technical choices.

### Autonomous Usage Possible
This guide can be used independently for any impact evaluation project, even outside the complete Digital Transversality approach.

---

## Next Steps

To concretely use this tree structure:

1. Select relevant indicators according to project context
2. Define measurement methods adapted to available budget  
3. Establish correlations specific to building/territory type
4. Configure critical thresholds according to regulatory and ethical context
5. Set up temporal monitoring system for impacts

This methodology constitutes the theoretical foundation for developing operational decision-support tools oriented toward sustainable human flourishing.