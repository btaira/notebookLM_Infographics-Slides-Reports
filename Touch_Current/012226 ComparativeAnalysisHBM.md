# A Comparative Analysis of Human Body Electrical Impedance Models for Electric Shock Hazard Assessment

## 1.0 Introduction to Human Body Impedance Modeling in Electrical Safety

Accurately modeling the electrical impedance of the human body is a cornerstone of modern electrical safety engineering. The development of effective safety standards, protective equipment, and safe-work protocols depends on a precise understanding of how electric current passes through the body. The relationship between the applied touch voltage and the resulting body current exhibits significant voltage-dependent non-linearity, making robust, evidence-based models essential for performing reliable hazard assessments and preventing injury or death from electric shock.

This report presents a synthesized and critical comparison of various electrical models of human body impedance. It draws from the foundational IEC 60479-1 standard, advanced physiological research into the mechanisms of skin resistance, and modern computational studies by Underwriters Laboratories (UL) that leverage high-fidelity virtual human models. The core purpose of this analysis is to demonstrate why legacy models, while foundational, are being superseded by computational approaches that reveal potentially critical underestimations of risk in current safety standards.

The analysis will trace the evolution of this field, beginning with the standardized lumped-parameter circuits that provide a practical basis for international safety requirements. It will then explore more nuanced circuit-based refinements before examining the underlying physiological phenomena that explain why simple models are fundamentally incomplete. Finally, the report will detail the shift toward sophisticated 3D electromagnetic simulations, which offer unparalleled insight into internal current distribution and provide computational proof of legacy models' shortcomings. This progression provides a comprehensive overview for electrical safety professionals seeking to understand both the established standards and the future direction of bioelectrical safety research. We begin with an examination of the most widely adopted foundational model.

## 2.0 The Foundational IEC 60479-1 Standard Model

The International Electrotechnical Commission (IEC) standard 60479-1, Effects of current on human beings and livestock, provides the international baseline for understanding and quantifying the physiological effects of electric shock. Its simplified electrical model of the human body is of strategic importance, offering a practical and standardized framework that enables engineers to design protective measures and establish consistent safety requirements worldwide. This model serves as the essential, albeit simplified, reference point against which more advanced methodologies are evaluated.

The standard defines the total impedance of the human body (ZT) as being composed of three core components: the internal impedance of the body (Zi) and the impedance of the skin (Zs) at the two points of electrical contact. The total impedance is represented as the vectorial sum of these elements.

As described in Figure 1 of the IEC 60479-1 standard, the model's schematic represents the total impedance (ZT) as the internal impedance (Zi) connected in series with two parallel resistor-capacitor (RC) circuits. Each of these RC circuits (Zs1 and Zs2) represents the impedance of the skin at the entry and exit points of the current. This configuration captures the fundamental resistive and capacitive nature of the body's response to alternating current.

According to the IEC standard, the total body impedance (ZT) is not a fixed value but is influenced by a range of physical and environmental factors, the quantitative impact of which is critical for hazard analysis.

* Touch Voltage and Current: There is a distinct inverse relationship between the applied touch voltage and the body's total impedance. As the touch voltage increases, the impedance of the skin decreases significantly, allowing more current to flow. For example, for large dry contact areas, the 50th percentile impedance drops from 1725 Ω at 50V to 1350 Ω at 100V, a decrease of nearly 22%.
* Contact Surface Area: The surface area over which contact is made drastically alters impedance. Based on data from Figures 7, 8, and 9 of the standard, large surface areas (on the order of 10,000 mm²) present a much lower impedance than medium (1,000 mm²) or small (100 mm²) surface areas under the same conditions.
* Skin Condition: The moisture level of the skin is a critical variable. For a large contact area at 100V, the 50th percentile impedance for dry skin is 1350 Ω (Table 1), which plummets by 44% to 750 Ω for water-wet skin (Table 2), and by 78% to 300 Ω for highly conductive saltwater-wet skin (Table 3), demonstrating the critical role of environmental conditions in hazard assessment.
* Frequency: Total body impedance is frequency-dependent. As detailed in Figures 10, 11, and 12, ZT generally decreases as the frequency of the AC source increases from 50/60 Hz into the kilohertz range, primarily due to the capacitive component of skin impedance.

While the IEC 60479-1 model is a vital tool for standardization and general hazard analysis, its simplifications represent a necessary compromise. Early attempts to address its shortcomings led to the development of more specialized circuit-based models designed to fix its flaws for specific applications.

## 3.0 Alternative Circuit-Based Models and Refinements

While the foundational IEC model is sufficient for general safety cases, different scenarios and measurement needs have necessitated the development of more nuanced or complex circuit-based models. These alternatives represent early attempts to fix the inherent flaws of the simple model, aiming to either facilitate specific types of safety testing or improve the model's fidelity by incorporating a wider range of empirical data.

Analysis of a Measurement-Specific Model

For the specific purpose of measuring reaction current—the threshold at which a person involuntarily reacts to a shock—a modified circuit is used. As shown in Figure 2 of the UL report, this circuit is distinguished from the general IEC model by the inclusion of a "Frequency Sensitive Network" composed of a 10 kΩ resistor and a 0.022 µF capacitor. This additional network is not part of the intrinsic body impedance itself; rather, it is integrated into the measurement circuit to correctly account for the frequency dependence of the human body's physiological reactions to current, a nuance the base model does not address.

Analysis of a Data-Driven Model

To create a model that more accurately reflects measured impedance over a broad frequency spectrum, researchers like Santis et al. have proposed more complex circuits. As presented in Figure 6 of the UL report, this model is a higher-order, multi-pole RC network. It was derived not from theoretical principles alone but from fitting the circuit's response to impedance measurements taken from a population of adults across a frequency range up to 110 MHz.

The effectiveness of this data-driven approach is demonstrated in Figure 7 of the UL report. The impedance curve of the "proposed circuit" closely tracks the actual "measured" impedance data across the entire frequency range. In contrast, the standard "IEC circuit" model provides a reasonable approximation at lower frequencies but flattens out and deviates significantly from measured reality at higher frequencies, revealing its limitations outside the standard 50/60 Hz domain.

Analysis of an Anatomically Distributed Model

Another refinement, sourced from IEC 60479-1 and shown in Figure 5 of the UL report, is a distributed internal impedance model. Its primary advantage over a simple lumped model is its granularity. Instead of representing the entire internal impedance (Zi) with a single value, this model assigns impedance percentages to different body parts, such as the arms, legs, and torso. This allows for a more detailed representation of current distribution along different pathways (e.g., hand-to-hand versus hand-to-foot). However, as noted in the UL report, this model has a key limitation: it only accounts for the resistive component of impedance and lacks any reactive (capacitive) components, limiting its accuracy for AC analysis.

These varied circuit-based approaches demonstrate a clear effort to add layers of specificity and accuracy. However, to truly understand their limitations, it is necessary to examine the deep biological reason why the body's impedance, particularly that of the skin, is so profoundly complex.

## 4.0 The Physiological Basis of Skin Impedance Non-Linearity

To fully appreciate why simple resistor-capacitor (RC) circuit models are fundamentally flawed, one must understand the underlying biological phenomena that govern the skin's electrical behavior. The skin, specifically the outermost layer known as the stratum corneum, is the primary barrier to electric current. The limitations of simple circuit models for skin impedance (Zs) become apparent when examining the complex physiological mechanisms that occur within this layer during an electric shock.

Research presented in the University of Pretoria dissertation, "THE VOLTAGE-CURRENT CHARACTERISTIC OF THE HUMAN SKIN," identifies two primary mechanisms responsible for the skin's highly non-linear and asymmetric electrical properties.

* Electroporation: This process is identified as a key factor in the breakdown of skin resistance. It occurs within the lipid bilayer membranes of the stratum corneum when a voltage is applied, specifically noted in the 10-20 V range. This voltage stress leads to the formation of transient pores in the cell membranes, causing a rapid and partially reversible decrease in skin resistance.
* Electro-osmosis: This phenomenon is proposed as the mechanism responsible for the observed asymmetry in the skin's voltage-current characteristic. Also occurring within the lipid bilayers, electro-osmosis involves the movement of fluid in response to an electric field, which can lead to different current flow characteristics depending on the polarity of the applied voltage.

Based on this physiological evidence, the common representation of skin impedance (Zs) as a simple parallel RC circuit is an oversimplification. Such a linear, symmetric model cannot inherently account for the dynamic, non-linear resistance breakdown caused by electroporation, nor can it replicate the asymmetric current flow attributed to electro-osmosis. The skin does not behave like a simple electronic component; its impedance is an emergent property of complex, voltage-dependent biological processes.

This deep physiological understanding highlights the inherent limitations of any lumped-parameter circuit model. It justifies the scientific progression toward more advanced, physics-based computational approaches that can provide computational proof of these legacy models' shortcomings.

## 5.0 The Evolution to 3D Electromagnetics and Advanced Metrics

The inherent limitations of circuit-based models have driven a necessary evolution toward 3D electromagnetics modeling. To understand the true distribution of current within the body's complex internal structures and to calculate sophisticated safety metrics related to specific organs, it is essential to move beyond abstract circuits to anatomically accurate computational models. This shift provides the computational proof of where and why legacy models may be insufficient.

The fundamental differences between circuit-based and 3D electromagnetics modeling are significant, as summarized below.

Feature	Circuit-Based Modeling	3D Electromagnetics Modeling
Representation	Lumped components (resistors, capacitors) representing entire body parts.	High-resolution 3D virtual human models (e.g., "Duke") with distinct tissues and organs.
Output	Total impedance (ZT) and touch current.	Detailed internal current density distribution, electric fields, and Specific Absorption Rate (SAR).
Insight Level	Provides a single value for impedance; lacks spatial detail.	Allows for analysis of current flow through specific organs, like the heart.
Key Advantage	Simplicity and ease of implementation for standardization.	High fidelity and predictive power for complex internal effects.

A prime example of a metric that is only accessible through 3D modeling is the Heart Current Factor (HCF). The HCF is a critical safety metric used to assess the risk of ventricular fibrillation—the most dangerous physiological effect of electric shock. It quantifies the fibrillation risk for different current pathways relative to a baseline path (left hand to feet). Because the HCF depends on the actual current density passing through the heart muscle, it is a value that simple circuit models are fundamentally incapable of calculating.

The 3D simulations from the UL report reveal critical discrepancies between modern computational results and established standards. Using the detailed "Duke" virtual human model, researchers calculated HCF values and compared them to the values in IEC 60479-1:

* For pathways distant from the heart, such as Left Foot to Right Foot, the UL 2017 model calculates an HCF of 0.01. While this is lower than the IEC standard's value of 0.04, both models correctly identify this as a low-risk pathway relative to the reference.
* For the Chest to Right Hand pathway, the UL model predicts an HCF of 1.6, which is higher than the IEC value of 1.3, suggesting a potentially greater risk than the standard assumes.
* Most notably, for the common Left Hand to Right Hand pathway, the UL model calculates an HCF of 1.0, whereas the IEC standard lists a value of 0.4. This finding is not an outlier; it aligns with a growing body of computational research. As shown in the UL report's comparative analysis (Table 7), studies by Tarao et al. (2009) and Freschi et al. (2013) also calculated significantly higher HCF values of 0.87 and 1.3, respectively. The consensus among these independent, modern 3D simulations suggests that the IEC standard's factor of 0.4 may underestimate the fibrillation risk for this common hand-to-hand pathway by more than double.

The 3D simulations reveal that the predicted HCF values are either in agreement with or, in several key cases, larger than those in the safety standards, implying a greater danger for certain pathways than is accounted for in current guidelines. Consequently, 3D modeling provides an indispensable tool for validating and critically re-evaluating the safety factors embedded in our existing electrical safety standards.

## 6.0 Synthesis and Conclusion

This analysis has traced the evolution of human body impedance modeling, demonstrating a clear progression from simplified abstraction to high-fidelity simulation. The journey began with the standardized IEC 60479-1 lumped-parameter circuit, a vital tool for establishing a practical baseline for safety. It advanced through various circuit-based refinements attempting to patch its flaws for specific applications. A deeper analysis of skin physiology revealed the non-linear phenomena of electroporation and electro-osmosis, explaining why simple circuits are fundamentally inadequate. This understanding culminated in the current state-of-the-art: 3D computational analysis, which provides urgent, quantitative evidence of where the legacy models fall short, particularly in calculating critical metrics like the Heart Current Factor.

The following table provides a final summary comparing the primary modeling approaches discussed in this report.

Model Type	Primary Strength	Key Limitation
IEC 60479-1 Standard Circuit	Simplicity and standardization for broad engineering application.	A simplified abstraction that cannot capture non-linear effects or internal current distribution.
Physiologically-Informed Concepts (Electroporation)	Provides the fundamental biological explanation for the skin's non-linear impedance.	A conceptual framework, not a direct engineering model for hazard calculation.
3D Electromagnetics Simulation	High-fidelity, anatomically accurate prediction of internal current density and organ-specific effects (e.g., HCF).	High complexity, computationally intensive, and dependent on accurate tissue property data.

For electrical safety professionals, the implications are clear. Standard circuit models, particularly the IEC 60479-1 framework, remain essential for practical, day-to-day safety design and compliance. However, it is crucial to recognize their inherent simplifications and the urgent need to consider the evidence from advanced modeling.

Advanced physiological and computational research, as demonstrated by the UL study, does more than simply refine existing standards—it critically challenges their underlying assumptions. The significant, multi-study discrepancies in metrics like the Heart Current Factor signal a potential gap between standardized safety values and biophysical reality. This research must inform the next generation of electrical safety standards, ensuring they are grounded not just in historical data but in the most accurate and predictive understanding of bioelectrical phenomena available.
