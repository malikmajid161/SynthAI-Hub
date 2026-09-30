# SynthAI Hub

Live server: http://31.97.113.9:8080/

## System Design

![System Design](assets/system_design.jpg)

## Project Description & Functionalities

**Syndata** is an advanced, multi-modal synthetic data generation platform. It is designed to safely synthesize realistic mock data for testing, AI training, and analytics while preserving privacy and data utility.

### Core Engines and Working:

1. **Tabular Data Engine:**
   - Ingests CSV files to learn statistical distributions.
   - Generates high-fidelity single-table synthetic data.
   - Supports PII anonymization, customizable null injection, and outlier simulation to test extreme edge cases.

2. **Relational Data Engine (SQLite):**
   - Parses multi-table schemas and synthesizes complex relational databases.
   - Automatically maintains primary/foreign key constraints and referential integrity across synthesized tables using SDV (Synthetic Data Vault).

3. **Document & OCR Engine:**
   - Processes document datasets (e.g., Kaggle OCR JSON layouts, invoices).
   - Generates synthetic document layouts and provides interactive HTML previews of the synthesized documents.

4. **Evaluation & Visualization:**
   - Built-in metrics (via \sdmetrics\) to compare the statistical similarity between real and synthetic data.
   - Interactive UI visualizations to review data profiles, distributions, and privacy preservation scores.

5. **Architecture & Isolation:**
   - A FastAPI orchestrator manages the backend, spawning isolated Python subprocess workspaces for each task.
   - Ensures robust multi-tenant execution and state management via an interactive web interface.

