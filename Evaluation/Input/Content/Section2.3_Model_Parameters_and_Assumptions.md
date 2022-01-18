### 2.3.1	Absorption

Absorption of carbamazepine and carbamazepine-10,11-epoxide observed in clinical studies can be fully explained by passive absorption.

### 2.3.2	Distribution

For both carbamazepine and carbamazepine-10,11-epoxide, the observed clinical data was described by choosing the partition coefficient calculation by `Rodgers and Rowlands` and cellular permeability calculation by `PK-Sim Standard`. 

### 2.3.3	Metabolism, Elimination and Induction

Carbamazepine is metabolized by CYP2B6, 2C8, 3A4, and UGT2B7 ([Kerr 1994](#5-References), [Pelkonen 2001](#5-References), [Staines 2004](#5-References)). and a minor fraction of the dose (approximately 1%) is excreted unchanged in urine ([Bernus 1994](#5-References), [Morselli 1975](#5-References)). Carbamazepine-10,11-epoxide is cleared by metabolism via epoxide hydroxylase 1 (EPHX1) and glomerular filtration ([Kitteringham 1996](#5-References)). 

Induction of CYP2B6 and 3A4 was taken into account ([Eichelbaum 1985](#5-References)) and it was assumed that carbamazepine also induces EPHX1 ([Eichelbaum 1985](#5-References)). Carbamazepine induces CYP2B6 and 3A4 via the CAR pathway ([Faucette 2007](#5-References)); therefore, the same EC<sub>50</sub> value was used in the model for induction of CYP2B6, 3A4, and EPHX1. The associated E<sub>max</sub> values were optimized.

### 2.3.4	Automated Parameter Identification

The parameter identification tool in PK-Sim<sup>®</sup> has been used to estimate selected model parameters. The result of the final parameter identification is shown in the table below:

| Model Parameter            | Optimized Value | Unit |
| -------------------------- | --------------- | ---- |
| **Carbamazepine** |  |  |
| `Lipophilicity` | 2.00   |        |
| `Specific clearance` (total hepatic clearance process) | 0.015 | 1/min |
| `kcat` (CYP3A4)<sup>a</sup>                             | 0.200           | 1/min  |
| `kcat` (→ CBZE via CYP3A4)<sup>b</sup>                  | 0.750           | 1/min  |
| `Emax` (CYP2B6)                                         | 17.0            |  |
| `Emax` (CYP3A4)                                         | 6.00            |        |
| `Emax` (EPHX1)                                          | 3.25            |        |
| `GFR fraction`                                          | 0.027           |        |
| `Dissolution time (50% dissolved)` (IR tablet, fasted)  | 200.0           | min    |
| `Dissolution shape` (IR tablet, fasted)                 | 0.740           |        |
| `Dissolution time (50% dissolved)` (IR tablet, fed)     | 100.0           | min    |
| `Dissolution shape` (IR tablet, fed)                    | 1.20            |        |
| `Dissolution time (50% dissolved)` (XR tablet, fasted) | 767.2 | min  |
| `Dissolution shape` (XR tablet, fasted) | 0.758 |   |
| `Dissolution time (50% dissolved)` (XR tablet, fed) | 436.4 | min |
| `Dissolution shape` (XR tablet, fed) | 1.159 | |
| `Dissolution time (50% dissolved)` (XR capsule, fasted) | 439.5 | min |
| `Dissolution shape` (XR capsule, fasted) | 0.794 | |
| `Dissolution time (50% dissolved)` (XR capsule, fed) | 361.4 | min |
| `Dissolution shape` (XR capsule, fed) | 2.127 | |
| **Carbamazepine-10,11-epoxide** |  | |
| `Lipophilicity` | 1.16 | |
| `Specific intestinal permeability (transcellular)` | 0.299 | cm/min |
| `Specific clearance` (EPHX1) | 0.010 | 1/min |
| `GFR fraction` | 0.213 | |
| `Dissolution time (50% dissolved)` | 200.0 | min |
| `Dissolution shape` | 0.754 | |

<sup>a</sup> refers to CYP3A4-mediated reaction forming other metabolites than carbamazepine-10,11-epoxide

<sup>b</sup> refers to CYP3A4-mediated reaction forming carbamazepine-10,11-epoxide


### 