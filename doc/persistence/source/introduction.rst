Introduction
============

FORM (Flexible-grained Object Reading/Writing Model)  is a configuration-driven persistence infrastructure, developed for Phlex :cite:`phlex_github`, providing a structured approach to data storage and retrieval for scientific computing workflows. FORM serves as a mediation layer between the phlex physics framework and storage systems, translating high-level data product concepts into persistence operations through declarative configuration. The design maintains clean separation between phlex-specific and persistence concerns, enabling future portability while meeting current Phlex requirements.

This document originated from the FORM design work started in 2025 and was subsequently organized into Sphinx documentation in February 2026. Its content primarily reflects the original design of FORM as the flexible I/O layer for Phlex. FORM has since evolved through Phlex v0.4, with significant additions to its technical implementation and design. :doc:`status-and-evolution` summarizes the architecture released in Phlex v0.4, records key milestones, and identifies remaining future work. Read it first for an overview of the current implementation.
