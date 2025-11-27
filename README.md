# OPTCELL_VASP: Constrained cell relaxation

The provided file enables constrained cell relaxation in VASP by modifying the cell degrees of freedom using an OPTCELL file. It allows you to fix specific lattice vectors or angles during relaxation, which is useful for certain symmetry constraints.

1. Copy the constr_cell_relax.F file to the src directory of your VASP root directory.
2. Recompile VASP

## Usage
- Use the OPTCELL file to specify which lattice vectors or angles to constrain.
- This feature only works with ISIF = 3 in your VASP input.

## OPTCELL File Format
Each line in the OPTCELL file corresponds to a lattice vector (A, B, C). Use 1 to allow relaxation and 0 to fix that component.

### Fix C vector:

110
110
000

### Fix A and B vectors:

000
000
001

### Fix angle between A and B vectors:

100
010
111

### Fix the angle between A and B, and fix C vector:

100
010
000

## How to Use
1. Rotate the AB axis to the xy plane (optional, for specific setups).
2. Create the OPTCELL file with your desired constraints.
3. Set ISIF = 3 in your VASP input.
4. Run your VASP job
