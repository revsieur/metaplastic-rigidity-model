## 2. Methods

### 2.1 Neuron-Only Baseline Model
To establish a baseline, we first implemented a biologically-plausible Actor-Critic agent based on the Frank (2005) model of the basal ganglia. This model uses a two-phase (plusminus) learning rule that is biologically analogous to synaptic eligibility and dopaminergic (RPE) modulation.

#### 2.1.1 The Minus Phase (Action Selection)
Action selection is determined by the Go and NoGo pathways. The activity of each pathway ($y^-$) is calculated as the dot product of the input state vector ($x$) and its respective synaptic weights ($W$)

$$y_{go}^- = W_{go} cdot x$$
$$y_{nogo}^- = W_{nogo} cdot x$$

The agent selects 'Go' if $y_{go}^-  y_{nogo}^-$ and 'NoGo' otherwise. This $y^-$ activity is stored as a primed state, biologically representing a synapse with glutamate-bound NMDARs.

#### 2.1.2 The Plus Phase (Learning)
Upon receiving feedback (reward or punishment), a phasic dopamine signal (the RPE, $delta$) modulates the primed $y^-$ activity to create a new unlocked $y^+$ activity. This represents the $text{Ca}^{2+}$ influx that follows NMDAR activation.

The synaptic weights are then updated by comparing the plus and minus phase activities, which is the snapshot learning rule

$$Delta W propto (y^+ - y^-) cdot x$$