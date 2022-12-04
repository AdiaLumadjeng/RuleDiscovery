# Rule Generation for Classification: Scalability, Interpretability, and Fairness

**Adia Lumadjeng, Tabea Röber, M. Hakan Akyüz, and Ş. Ilker Birbil**


We introduce a new rule-based optimization method for classification with constraints. The proposed method
takes advantage of linear programming and column generation, and hence, is scalable to large datasets. Moreover, the method returns a set of rules along with their optimal weights indicating the importance of each rule for learning. Through assigning cost coefficients to the rules and introducing additional constraints, we show that one can also consider inter pretability and fairness of the results. We test the performance of the proposed method on a collection of datasets and present two case studies to elaborate its different aspects. Our results show that a good compromise between interpretability and fairness on the one side, and accuracy on the other side, can be obtained by the proposed rule-based learning method.

You can find the details of both algorithms in [our manuscript](https://arxiv.org/abs/2104.10751).

This [notebook](RuleDiscovery.ipynb) illustrates how to use RUX and RUG.

## Installation

 1. Install [Anaconda Distribution](https://www.anaconda.com/products/individual).

 2. Create a new environment and install the necessary packages:

 `conda create -n rulediscovery --channel=conda-forge python=3.8 numpy pandas scikit-learn cvxpy cvxopt gurobi`

 3. Activate the current environment:

 `conda activate rulediscovery`

 4. Check whether the installation works with the either of the following test files.

---

**OPTIONAL:**

To use the Gurobi solver, you need to first install
it. The solver is freely available for academic use. Check the
[related
page](https://www.gurobi.com/academia/academic-program-and-licenses/)
on Gurobi's website.

--
## Testing the code
The code contains the following files to reproduce the results of our manuscript:
 1. `ruxg_testing.py`

 2. `fairruxg_testing.py` is used to test the FairRUX and FairRUG algorithms for the eight datasets COMPAS, adult, default, law, attrition, recruitment, student and nursery. To reproduce the results of Table EC.5 in our manuscript, the tests are run with `randomState=21`, `maxDepth=3`, `numEstimators=100` and we set the value of `fairness_eps` to 0 for COMPAS, adult and default, 0.01 for attrition, recruitment and student, and 0.025 for law and nursery. Running the file should immediately start the 10-fold cross validation and write the results to .txt files in the folder FairnessResults (link).

 3. `LoanCase`

 4. `COMPASCase`

