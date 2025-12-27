## Iterative Exploration of Molecular Bandgap with Gemini

This is a simple of concept I did as part of my application for a PhD position at the LIAC. During my interview with @philippe and @samuel, I proposed a project using an LLM to be the 'reasoning engine' in an experimentation loop. After the interview, I wanted to see how this system system would work. Here, Gemini is given a goal and iteratively predicts molecular structures (SMILES strings) and validates them using the PySCF computational chemistry package. 

This is written in python and can be run in google colab.

- Starting Point: Benzene (Bandgap: 14.39 eV)
- Target: Aromatic molecule with a bandgap of ~4.5 eV
- Objective: Gemini must iteratively modify the ring structure to lower the bandgap.

### Methodology:
We tested three distinct prompting strategies, repeating each experiment 3 times:

- **One-shot prediction**: (One Shot Attempts) Single direct attempt.
- **Few-shot prediction** (Blind): Iterative attempts without explicit reasoning traces.
- **Few-shot prediction** (Reasoning): Iterative attempts requiring the model to explain its logic.

### Key Findings:
- One-shot prediction failed to perform effectively in this context.
- Few-shot predictions (both with and without reasoning) showed similar performance in reaching the target bandgap.
- **Critical Distinction**: The "Blind" model (no reasoning) occasionally suggested molecules that were computationally too expensive/large for the simulation environment. The "Reasoning" model avoided this issue, suggesting more practical candidates.

The image shows the models' convergence on the target bandgap.

### Conclusion:
While further exploration is needed to definitively quantify the improvement in predictive accuracy provided by reasoning, there is evidence that reasoning capabilities lead to more practical and feasible chemical suggestions.

With a more advance set-up, I would like to apply this to the problem of multi-step synthesis. If anyone wants to discuss this idea, I'd love to connect!



