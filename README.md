# ZD1694-analysis-using-molecular-dynamic-simulation

This repository contains scripts for running molecular dynamics simulations of a drug molecule in both **shielded** and **non-shielded** configurations using **LAMMPS** and **VMD TopoTools**.

---

## 🔧 Setup Instructions

### Install and Configure **TopoTools 1.9**
Ensure **TopoTools 1.9** is installed by copying it to the appropriate **VMD plugin** directory:

```bash
sudo cp -r topotools1.9 /usr/local/lib/vmd/plugins/noarch/tcl
```

Check the installation by starting VMD and running:

package require topotools

- topo guessdihedrals wbo
- topo guessbonds
- topo guessangles
- pbc set {100 100 100}
- set box1 [pbc box_draw -width 1 -color black]
- topo writelammpsdata final.data

```
lmp < 1.in   # Run non-shielded drug simulation
lmp < 2.in   # Run shielded drug simulation
```

![1](https://github.com/user-attachments/assets/baf00433-11a0-4195-99c1-a6aaca1dc378)
![2](https://github.com/user-attachments/assets/24d48926-ab01-4615-b543-69583862367b)



📁 simulation_project
 ├── 📄 README.md        # This documentation
 ├── 📄 1.in             # LAMMPS input file (non-shielded drug)
 ├── 📄 2.in             # LAMMPS input file (shielded drug)
 ├── 📄 mw.data      # Generated LAMMPS data file for shielded
 ├── 📄 noshield.data      # Generated LAMMPS data file for nonshielded
 
