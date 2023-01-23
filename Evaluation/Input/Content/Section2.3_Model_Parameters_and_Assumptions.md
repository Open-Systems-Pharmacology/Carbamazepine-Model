### 2.3.1	Absorption

Absorption of carbamazepine from the gastrointestinal tract can be fully explained by passive diffusion; active uptake by drug transporters does not seem to play a role. Intestinal permeability was observed to be not a rate-limiting step in drug absorption. The solubility of carbamazepine following administration of the IR tablet was fixed to the mean value (308 mg/L at a pH of 6.7) reported by several studies in fasted human intestinal fluid ([Annaert 2010](#5-references), [Söderlind 2010](#5-references), [Clarysse 2011](#5-references)).

### 2.3.2	Distribution

Plasma protein binding of carbamazepine was fixed to 75.7% as reported by Morselli et al. for healthy subjects ([Morselli 1975](#5-references)). The distribution of carbamazepine throughout the body was found to be best described by the partition coefficient calculation by `Rodgers and Rowlands` and cellular permeability calculation by `PK-Sim Standard`. 

### 2.3.3	Metabolism, Excretion and Induction

#### Metabolism

Carbamazepine metabolism is complex involving multiple enzymes with more than 30 metabolites identified ([Lertratanangkoon 1982](#5-references)). Several *in vitro* studies suggest involvement of CYP1A2, 2A6, 2B6, 2C8, 2E1, 3A4, and UGT2B7 in carbamazepine metabolism ([Cazali 2003](#5-references), [Kerr 1994](#5-references), [Pearce 2002](#5-references), [Pelkonen 2001](#5-references), [Staines 2004](#5-references)). 

In various *in vitro* assays, the biotransformation to the main metabolite, carbamazepine-10,11-epoxide, appears to be mainly catalyzed by CYP3A4 with minimal contribution by CYP2C8 ([Cazali 2003](#5-references), [Egnell 2003](#5-references), [Kerr 1994](#5-references)). For example, Egnell et al. report that, at equimolar amounts of recombinantly expressed CYP enzymes, the activity of CYP3A4 towards carbamazepine was more than 20-fold higher than that of CYP2C8 ([Egnell 2003](#5-references)). Therefore, carbamazepine epoxidation was modeled via CYP3A4 only.

Further oxidative metabolism pathways include 2- and 3-hydroxylation. The formation of 2-hydroxycarbamazepine is mediated by several CYP enzymes *in vitro* (including CYP1A2, 2A6, 2B6, 2E1, and 3A4); though, the contribution of any of these isoforms does not exceed 50% of the total formation ([Pearce 2002](#5-references)). In experiments with liver slices, 2-hydroxylation appears to be a minor elimination pathway (1-2 % of total clearance) as reported by Pelkonen et al. ([Pelkonen 2001](#5-references)). Hence, 2-hydroxylation was not accounted for in the PBPK model. 

The formation of 3-hydroxycarbamazepine also appears to constitute a minor metabolism pathway ([Pelkonen 2001](#5-references)); still, in human liver microsomes, 3-hydroxycarbamazepine was formed at rates ~25 times greater than those of 2-hydroxycarbamazepine ([Pearce 2002](#5-references)). The responsible enzyme for 3-hydroxylation *in vitro* seems to be CYP2B6, although a minor contribution by CYP1A2, 2A6, and 3A4 cannot be ruled out ([Pearce 2002](#5-references)). In the PBPK model, 3-hydroxylation was implemented as CYP2B6-mediated reaction.

N-glucuronidation of carbamazepine in human liver microsomes and baculovirus-infected insect cells expressing human UGTs was also observed with UGT2B7 appearing to be the responsible enzyme for this reaction ([Staines 2004](#5-references)). Thus, the PBPK model also includes UGT2B7-mediated N-glucuronidation of carbamazepine.

In summary, the following three metabolic pathways, each mediated by a specific enzyme, were implemented in the PBPK model:

* 10,11-epoxidation via CYP3A4
* 3-hydroxylation via CYP2B6
* N-glucuronidation via UGT2B7

Since no clinical mass balance data were found for these three pathways, the following clearance kinetics in human liver microsomes reported for each pathway were initially implemented in the PBPK model:

| Biotransformation pathway | K<sub>m</sub> [µM] | V<sub>max</sub> [pmol/min/mg microsomal protein] | Source                         |
| ------------------------- | ------------------ | ------------------------------------------------ | ------------------------------ |
| 10,11-epoxidation         | 808                | 726                                              | [Sakamoto 2013](#5-references) |
| 3-hydroxylation           | 235                | 49.0                                             | [Pearce 2002](#5-references)   |
| N-glucuronidation         | 234                | 3.5                                              | [Staines 2004](#5-references)  |

The following enzymatic content in human liver microsomes was assumed:

| Enzyme | Enzyme content [pmol/mg microsomal protein] | Source                          |
| ------ | ------------------------------------------- | ------------------------------- |
| CYP3A4 | 108                                         | [Rodrigues 1999](#5-references) |
| CYP2B6 | 39                                          | [Rodrigues 1999](#5-references) |
| UGT2B7 | 82.9                                        | [Achour 2014](#5-references)    |

The expression profiles for these enzymes were loaded from the 'PK-Sim<sup>®</sup> Ontogeny Database Version 7.3' ([PK-Sim Ontogeny Database Version 7.3](#5-references)) using RT-PCR as data source for each enzyme.

Upon implementation of these enzyme clearance pathways, it was seen that total clearance was slightly overestimated in the PBPK model. Therefore, the k<sub>cat</sub> values of each enzyme were optimized during parameter identification; to respect the initial mass balance of these biotransformation reactions as reported in human liver microsomes, the k<sub>cat</sub> values were not fitted independently but were varied together by the same factor. 

#### Excretion

A minor fraction of the carbamazepine dose (approximately 1%) is excreted unchanged in urine ([Bernus 1994](#5-references), [Morselli 1975](#5-references)). In the model, unchanged renal excretion was implemented as glomerular filtration with the parameter `GFR fraction` being fitted to the clinical excretion data reported by Bernus et al. ([Bernus 1994](#5-references)).

#### Induction

Carbamazepine induces CYP2B6 and 3A4 via the CAR- and PXR-pathway ([Faucette 2007](#5-references), [Williamson 2016](#5-references)). CYP2B6 induction was informed based on *in vitro* experiments conducted by Faucette et al. ([Faucette 2004](#5-references)). These authors reported the induction of CYP2B6 activity at various carbamazepine concentrations in three preparations of primary human hepatocytes. The reported data suggest linear induction in the tested carbamazepine concentration range. A linear-mixed effects model was fitted to the reported data; the fitted slope was 0.149. To implement a linear induction in the PBPK model, the EC<sub>50</sub> value of the E<sub>max</sub> model was set to an arbitrarily high value (1000 µM) and E<sub>max</sub> was then calculated as product of the fitted slope value and EC<sub>50</sub> resulting in a value of 149.

CYP3A4 induction was initially parameterized based on internal *in vitro* experiments and calibrated with rifampicin induction data as described by Almond et al. ([Almond 2016](#5-references)). This resulted in an EC<sub>50</sub> of 63.0 µM and an E<sub>max</sub> of 5.39. Simulated carbamazepine plasma concentrations in steady-state indicated that the induction was underestimated; therefore, the calibrated EC<sub>50</sub> value was optimized during parameter identification, while the calibrated E<sub>max</sub> value was kept fixed. 

### 2.3.4	Automated Parameter Identification

The parameter identification tool in PK-Sim<sup>®</sup> has been used to estimate the model parameters described above. The result of the parameter identifications is shown in the table below:

| Model Parameter            | Optimized Value | Unit |
| -------------------------- | --------------- | ---- |
| `Lipophilicity` | 2.01  |        |
| `kcat` (CYP3A4)                                             | 5.01 | 1/min |
| `kcat` (CYP2B6)                          | 0.936   | 1/min  |
| `kcat` (UGT2B7)       | 0.0669 | 1/min  |
| `GFR fraction`                              | 0.0240       |  |
| `EC50` (CYP3A4)                                      | 27.2       | µM |
| `Dissolution time (50% dissolved)` (IR tablet, fasted)  | 109         | min    |
| `Dissolution shape` (IR tablet, fasted)                 | 0.689        |        |
| `Dissolution time (50% dissolved)` (XR formulation, fasted) | 315        | min    |
| `Dissolution shape` (XR formulation, fasted)   | 1.23         |        |
| `Solubility at ref pH` -- for XR formulations only | 546 | mg/L |

