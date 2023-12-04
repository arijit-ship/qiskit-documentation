---
title: level_1_pass_manager
description: API reference for qiskit.transpiler.preset_passmanagers.level_1_pass_manager
in_page_toc_min_heading_level: 1
python_api_type: function
python_api_name: qiskit.transpiler.preset_passmanagers.level_1_pass_manager
---

# level\_1\_pass\_manager

<span id="qiskit.transpiler.preset_passmanagers.level_1_pass_manager" />

`level_1_pass_manager(pass_manager_config)`

Level 1 pass manager: light optimization by simple adjacent gate collapsing.

This pass manager applies the user-given initial layout. If none is given, and a trivial layout (i-th virtual -> i-th physical) makes the circuit fit the coupling map, that is used. Otherwise, the circuit is mapped to the most densely connected coupling subgraph, and swaps are inserted to map. Any unused physical qubit is allocated as ancilla space. The pass manager then unrolls the circuit to the desired basis, and transforms the circuit to match the coupling map. Finally, optimizations in the form of adjacent gate collapse and redundant reset removal are performed.

<Admonition title="Note" type="note">
  In simulators where `coupling_map=None`, only the unrolling and optimization stages are done.
</Admonition>

**Parameters**

**pass\_manager\_config** ([`PassManagerConfig`](qiskit.transpiler.PassManagerConfig "qiskit.transpiler.passmanager_config.PassManagerConfig")) – configuration of the pass manager.

**Return type**

[`PassManager`](qiskit.transpiler.PassManager "qiskit.transpiler.passmanager.PassManager")

**Returns**

a level 1 pass manager.

**Raises**

[**TranspilerError**](qiskit.transpiler.TranspilerError "qiskit.transpiler.TranspilerError") – if the passmanager config is invalid.
