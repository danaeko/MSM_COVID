## Markov State Model Analysis

A series of MD equilibrium trajectories of the 3CL-Pro monomers (20 x 3.0μs = 60μs) of SARS-CoV-2 main protease under different salts/ionic strengths, without inhibitors, was obtained. A major part of the 3CL-Pro conformational phase space should have been explored through these simulations. The all-atom MD simulations were combined with Markov state model (MSM) theory to enable the extraction of long-time-scale individual monomer dynamics from rather short-time-scale MD trajectories of different states. The application and accuracy of the powerful MSM theory have been demonstrated in many cases through experiments that include protein−protein or protein–drug binding kinetics, as well as protein folding rates and protein dynamics.

The objective was to approximate the slow dynamics in a statistically efficient manner. Therefore, a lower-dimensional representation of the simulation data was necessary. To achieve this reduction in dimensionality, time-structure independent components analysis (tICA) was employed. This method provided a reduced-dimensional representation of the molecular simulation data and facilitated the decomposition of the system into the discrete Markovian states required for MSM estimation. The conformations of the system were projected onto these slowest modes, as defined by the tICA method, and the trajectory frames were subsequently clustered into 100 cluster centers (microstates) using k-means clustering, as implemented in PyEMMA. 

The conformational changes of the system were simulated as a Markov chain under the assumption that transitions between different conformations were sampled at sufficiently long time intervals to ensure that each transition was Markovian. This condition implies that a transition from one conformation to another is independent of previous transitions, making the MSM a memoryless model. The uncertainty bounds were computed using a Bayesian scheme. It was found that the slowest implied timescales converge quickly and remain constant within a 95% confidence interval for lag times above 50 ns. The validation procedure followed a standard approach in the MSM field, with a lag time of 50 ns being selected for Bayesian model construction. The resulting models were validated through the Chapman–Kolmogorov (CK) test.

Subsequently, the MSMs that resulted were further coarse-grained into a smaller number of three metastable states or microstates using PCCA++, as implemented in PyEMMA. The optimal number of microstates (three) was proposed based on the VAMP2-score. Both the convergence of the implied timescales and the CK test confirmed the validity and convergence of the MSM. The CK test indicated that predictions from the constructed MSM were in good agreement with MSMs estimated with longer lag times. Thus, the model was found to accurately describe the long-time-scale behavior of the system within error.

The tICA method identified the torsional angles of the following 3CL-Pro residues as the most important features: 3, 4, 5, 6, 84, 135, 141, 164, 167, 171, 175, 178, 179, 180, 190, 195, 217, 284, 285, 286, 290, 291, 300, and 301. A series of thresholds was set for the coefficients in the tICA vectors to make this selection. Initially, a threshold of 0.09 was used, followed by thresholds of 0.04, 0.085, and finally 0.075. The previously mentioned 3CL-Pro residues were identified as a result of this process. The selection of these thresholds was guided by an analysis of different thresholds, the VAMP2-score, and the states projected onto the first two independent components. The exact functions of the first two tICA components were reported as a linear combination of cosine/sine functions of the associated torsional angles.

#### References
1. Plattner, N.; Noé, F. Protein conformational plasticity and complex ligand-binding kinetics explored by atomistic simulations and Markov models. Nat. Commun. 2015, 6, 7653, doi:10.1038/ncomms8653.

2. Plattner, N.; Doerr, S.; De Fabritiis, G.; Noé, F. Complete protein–protein association kinetics in atomic detail revealed by molecular dynamics simulations and Markov modelling. Nat Chem 2017, advance on, doi:10.1038/nchem.2785. 

3. Voelz, V.A.; Bowman, G.R.; Beauchamp, K.; Pande, V.S. Molecular Simulation of ab Initio Protein Folding for a Millisecond Folder NTL9(1−39). J. Am. Chem. Soc. 2010, 132, 1526–1528, doi:10.1021/ja9090353.

4. Durrant, J.D.; Kochanek, S.E.; Casalino, L.; Ieong, P.U.; Dommer, A.C.; Amaro, R.E. Mesoscale All-Atom Influenza Virus Simulations Suggest New Substrate Binding Mechanism. ACS Cent. Sci. 2020, 6, 189–196, doi:10.1021/acscentsci.9b01071.

5. Scherer, M.K.; Trendelkamp-Schroer, B.; Paul, F.; Pérez-Hernández, G.; Hoffmann, M.; Plattner, N.; Wehmeyer, C.; Prinz, J.-H.; Noé, F. PyEMMA 2: A Software Package for Estimation, Validation, and Analysis of Markov Models. J. Chem. Theory Comput. 2015, 11, 5525–5542, doi:10.1021/acs.jctc.5b00743.

6. Noé, F. Probability distributions of molecular observables computed from Markov models. J. Chem. Phys. 2008, 128, 244103, doi:10.1063/1.2916718.

7. Trendelkamp-Schroer, B.; Wu, H.; Paul, F.; Noé, F. Estimation and uncertainty of reversible Markov models. J. Chem. Phys. 2015, 143, 174101, doi:10.1063/1.4934536.

8. Wu, H.; Noé, F. Variational Approach for Learning Markov Processes from Time Series Data. J. Nonlinear Sci. 2020, 30, 23–66, doi:10.1007/s00332-019-09567-y.
