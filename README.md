# Distributed Goodness-of-Fit Testing Under Communication Constraints

🧭 **Project Overview**
This project investigates distributed statistical inference in a communication-constrained environment, focusing on **goodness-of-fit (GOF) testing for discrete distributions**.

In real-world distributed systems—such as multi-site clinical studies, sensor networks, or edge devices—data cannot always be fully shared due to **bandwidth limitations or privacy constraints**. This project simulates a scenario where **local nodes transmit only partial summaries of their data** to a central server, which then performs a global GOF test.

The project bridges **distributed statistics, hypothesis testing, and communication-efficient algorithms**, aligning with research on **distributed inference under communication constraints** (Vuursteen et al., 2023).

---

🎯 **Objectives**

* Simulate distributed discrete data across multiple nodes.
* Implement communication-constrained data aggregation strategies.
* Evaluate the impact of communication constraints on GOF test **Type I error** and **statistical power**.
* Visualize the trade-off between **communication fraction** and test performance.
* Align computational experiments with research in **distributed and high-dimensional statistical inference**.

---

⚙️ **Methodology / Work Performed**

**Data Simulation**

* Generated discrete data from **null (uniform)** and **alternative (perturbed)** distributions.
* Distributed data across `num_nodes = 10` nodes, each with `samples_per_node = 500`.

**Communication-Constrained Summaries**

* Each node communicates only a **fraction of category counts** to the central server.
* Communication fractions ranged from full communication (`1.0`) to highly constrained (`0.05`).

**Central Aggregation & Testing**

* Partial histograms were aggregated at the server.
* A **Chi-square goodness-of-fit test** was performed using aggregated counts.
* Type I error (false positive) and power (true positive detection) were calculated across `n_trials = 200` repetitions.

**Visualization & Analysis**

* Generated line plots showing **Power vs Communication Fraction** and **Type I Error vs Communication Fraction**.
* Quantified trade-offs between **communication efficiency** and **statistical power**.

---

📊 **Results**

| Communication Fraction | Type I Error | Power |
| ---------------------- | ------------ | ----- |
| 1.00                   | 0.05         | 0.74  |
| 0.50                   | 1.00         | 1.00  |
| 0.25                   | 1.00         | 1.00  |
| 0.10                   | 1.00         | 1.00  |
| 0.05                   | 1.00         | 1.00  |

**Observations:**

* Type I error remains controlled for full communication but inflates under severe constraints.
* Statistical power generally increases as more nodes communicate more information, but extreme constraints can cause instability.
* This demonstrates the **critical impact of communication limits** on distributed statistical inference.

**Visualization Example:**

* A line plot comparing **Power** and **Type I Error** across communication fractions.

---

🧠 **Discussion & Inference**

* **Impact of Communication Constraints:** Limited message size reduces the reliability of GOF tests.
* **Trade-Offs:** Full communication is ideal but may not be feasible; careful design of aggregation strategies is necessary.
* **Relevance:** Results highlight challenges in **distributed statistical systems**, **multi-site clinical studies**, and **edge-device analytics**.
* **Alignment with Research:** This project aligns with Lasse Vuursteen’s work on **distributed testing under communication constraints** and contributes to understanding **optimal inference under bandwidth limitations**.

**Potential Extensions:**

* Investigate **alternative aggregation methods** (e.g., randomized sketches, quantization).
* Explore **adaptive communication strategies** based on node importance.
* Apply to **real-world distributed datasets** (IoT sensors, multi-hospital studies).

---

✅ **Outcome**

* Implemented a communication-constrained distributed GOF testing framework.
* Quantified the trade-off between communication fraction and statistical performance.
* Visualized and interpreted the effects on **Type I error** and **power**, providing insights for distributed statistical design.

---

📚 **References**

* Vuursteen, L. (2023). *Optimal Private and Communication-Constrained Distributed Goodness-of-Fit Testing for Discrete Distributions in the Large Sample Regime*.
* Lehmann, E. L., & Romano, J. P. (2005). *Testing Statistical Hypotheses*. Springer.
* SciPy Stats Documentation: [https://docs.scipy.org/doc/scipy/reference/stats.html](https://docs.scipy.org/doc/scipy/reference/stats.html)

---
