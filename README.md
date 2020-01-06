## Online Supplement of:

# *Conflict-Driven Heuristics for Mixed Integer Programming*

##### Jakob Witzig[^1] and Ambros Gleixner[^2]

###### Zuse Institute Berlin, Takustr. 7, 14195 Berlin
___

This online supplement provides tables in CSV format with detailed results of the computational experiments conducted for the paper "Conflict-Driven Heuristics for Mixed Integer Programming" submitted to INFORMS Journal on Computing.

In the experiments, two different ways of combining primal heuristics and conflict analysis were compared to SCIP 6.0.

As test set we used a union of MIPLIB 3, MIPLIB 2003, MIPLIB 2010, and the Cor@l benchmark set. After removing all duplicates and problems that are known to be numerically unstable, the test set consists of 488 publicly available MIP problems, which we will refer to as MMMC.

To address performance variability, all experiments were run with four different random seeds. All data provided in this repository represents data where all settings considered in a respective experiment finished without error (e.g., numerical violations). Thus, for some instance less than four observations are available.

The repository is organized as follows. CSV data files of all experiments conducted with Farkas diving or conflict diving are stored in `farkasdiving` or `conflictdiving`.

#### Experiments

The following experiments where conducted:
###### Farkas diving:
* SCIP with default settings (baseline) vs. Farkas diving (`farkasdiving/MMMc_farkasdiving_vs_default_clean.csv`)
* Same as above but w/ and w/o adding solutions and analyzing infeasibility detected during Farkas diving (`farkasdiving/MMMc_farkasdiving_vs_default__nosols__noconfs_clean.csv`)

###### Conflict diving:
* SCIP with w/o coefficient diving vs. SCIP w/ coefficient diving (equivalent to SCIP with default settings) vs. SCIP w/o coefficient diving and with conflict diving (`conflictdiving/MMMc_default_coef_conf_clean.csv`)
* Same as above but w/ and w/o adding solutions and analyzing infeasibility during coefficient diving and conflict diving, respectively (`conflictdiving/MMMc_default_coef_conf__noconfs_nosols_clean.csv`)

#### CSV data details

All instance features, e.g., solving time or explored tree nodes, are always given with respect to a setting `s`:
* `default`
* `farkasdiving`
* `farkasdiving-no-confs`
* `farkasdiving-no-sols`
* `no-coefdiving`
* `coefdiving`
* `conflictdiving-no-coefdiving`


All CSV data contains the following columns:
* `ProblemName` : The name of the instance
* `T_s` : Absolute solving time in seconds
* `TQ+1_s` : Relative solving time with a shift of 1
* `N_s` : Absolute number of explored tree nodes
* `NQ+100_s` : Relative number of explored tree nodes with a shift of 100

The following instance features are only present for some of the experiments:

###### Farkas diving

* `DivingSolsMax_s` : The maximal number of feasible solutions found by a single diving heuristics. This corresponds to the virtual best diving heuristic w.r.t feasible solutions
* `DivingConfsMax_s` : The maximal number of conflicts found by a single diving heuristics. This corresponds to the virtual best diving heuristic w.r.t conflicts
* `DivingBestSolsMax_s` : The maximal number of improving solutions found by a single diving heuristics. This corresponds to the virtual best diving heuristic w.r.t improving solutions
* `FDSols_s` : Number of feasible solutions found by Farkas diving
* `FDBestSols_s` : Number of improving solutions found by Farkas diving
* `FDConfs_s`: Number of conflicts found by Farkas diving

###### Conflict diving

* `CoefSols_s` : Number of feasible solutions found by coefficient diving
* `CoefBestSols_s` : Number of improving solutions found by coefficient diving
* `CoefConfs_s` : Number of conflicts found by coefficient diving
* `CoefAvgDepth_s` : Average length of diving paths explored by coefficient diving
* `ConfSols_s` : Number of feasible solutions found by conflict diving
* `ConfBestSols_s` : Number of improving solutions found by conflict diving
* `ConfConfs_s` : Number of conflicts found by conflict diving
* `ConfAvgDepth_s` : Average length of diving paths explored by conflict diving

[^1]: <witzig@zib.de>
[^2]: <gleixner@zib.de>


