Status and Evolution
====================

This section summarizes FORM as released in the current Phlex release (v0.4), the major capabilities delivered in each release, and the work that remains. The following sections — :doc:`system-overview`, :doc:`architecture` and :doc:`detailed-design` — preserve the original design prototype and provide historical design context. Where that design differs from the released implementation, this section describes the current state.

Release Milestones
------------------

**Phlex v0.1 — Initial design prototype**

FORM began as a design effort to provide a flexible I/O layer for Phlex. The initial prototype established the main architectural concepts for separating storage technologies from their underlying data formats and for addressing products through a hierarchical data model. The design was initially developed against a ``mock_phlex`` stand-in for the framework.

**Phlex v0.2 — First released ROOT TTree write support**

FORM delivered ROOT TTree write support, making its first persistence functionality available in a Phlex release.

**Phlex v0.3 — Initial ROOT TTree read support**

FORM added a functional ROOT TTree read prototype, establishing an initial end-to-end workflow for writing and reading persisted data. It also introduced support for user-defined data types, allowing users to extend FORM's type support beyond the built-in types.

**Phlex v0.4 — Initial ROOT RNTuple write/read Support and Persistent Navigation**

FORM introduced initial ROOT RNTuple read/read support and extended its write path with a persistent navigation layout and product dictionary, describing how products map to their stored data. This release also added support for multiple output destinations and for writing TTree and RNTuple data to the same ROOT file. RNTuple support is enabled by default in Phlex installations.

The persisted navigation lays the groundwork for navigation-driven reading. However, the v0.4 reader still relies on the existing index-based lookup mechanism and does not yet use the new navigation metadata.

Current Capabilities
--------------------

As released in Phlex v0.4, FORM provides:

* **ROOT persistence:** Both ROOT TTree and RNTuple write and read support.
* **Multiple output destinations:** A single ``form_module`` can write to multiple destinations.
* **Mixed storage technologies:** TTree and RNTuple output can coexist in a single ROOT file.
* **Persistent navigation:** The writer records navigation tables and a product dictionary to describe the relationship between data cells, products, and their stored payloads.

These capabilities represent the current released functionality. The detailed organization of products, storage containers, navigation tables, and physical row spaces is described in :doc:`architecture` and :doc:`detailed-design`.

Current Limitations and Future Work
-----------------------------------

**Navigation-driven reading**

The v0.4 reader still locates products through the existing per-row-space index containers. It does not yet consult the navigation tables or product dictionary written by the v0.4 writer. Integrating these metadata structures into the read path remains future work.

**Navigation layout versioning**

The persisted navigation layout does not yet have its own versioning mechanism. Defining and maintaining a versioned navigation format remains future work.

**Further development**

FORM's design and implementation will continue to evolve as the read path, navigation model, and persistence format mature. Future design changes should be reflected in this overview so that it remains an accurate account of the capabilities delivered in each Phlex release.
