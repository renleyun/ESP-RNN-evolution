# 🧠 ESP-RNN-Evolution  
**Neuroevolution: Optimization of a Fully Connected Recurrent Neural Network using the ESP Algorithm**  
*Course project, Tomsk Polytechnic University*  

---

## 📘 Project Overview  

This project implements the **ESP (Enforced SubPopulations)** neuroevolutionary algorithm to train a **fully connected recurrent neural network (RNN)** with a single hidden layer for continuous control tasks in the **Gymnasium** reinforcement learning environment.  

Unlike gradient-based optimization, ESP evolves network weights through cooperative co-evolution of neuron subpopulations, enabling adaptive control in complex environments without backpropagation.  
The main experimental environment is **BipedalWalker-v3**, where the agent learns to walk bipedally through trial and error.  

---

## ⚙️ Experimental Environment  

| Module | Version | Description |
|--------|----------|-------------|
| Python | 3.10+ | Programming language |
| NumPy, Matplotlib | Latest | Numerical computation and visualization |
| NetworkX | Latest | Network structure visualization |
| Gymnasium[box2d] | 1.0+ | Reinforcement learning toolkit |
| BipedalWalker-v3 | Default | Continuous control environment |

To change the environment, modify in the code:
```python
env_name = "Pendulum-v1"  # or "CartPole-v1", etc.
```

---

## 🧩 Objectives  

- Implement the ESP neuroevolutionary algorithm;  
- Explore the performance of a recurrent neural network in continuous control;  
- Analyze spectral radius dynamics and network stability;  
- Visualize network structure, weight distribution, and evolutionary progress;  
- Compare convergence characteristics across generations.  

---

## 📊 Results  

The project produces several visual outputs:  

1. **RNN Structure Graph** — illustrates input, hidden, and output connections;  
2. **Recurrent Weight Heatmap (W_hh)** — visualizes internal weight evolution;  
3. **Spectral Radius Curve** — reflects dynamic stability of the recurrent layer;  
4. **Hidden State Trajectories** — show neuron activations over time;  
5. **Convergence Curve** — compares best and average fitness values by generation.  

---

## 🧠 Algorithm Description  

The **ESP (Enforced SubPopulations)** algorithm divides the hidden layer into independent subpopulations.  
Each subpopulation evolves separately through crossover and mutation, representing candidate neurons.  
At each evaluation step, one neuron is sampled from each subpopulation to assemble a complete RNN.  
The network is then evaluated in the environment, and the total reward (fitness) is evenly distributed among all participating neurons.  

Main steps:  
1. Initialize multiple subpopulations;  
2. Sample one neuron from each to form a complete RNN;  
3. Evaluate the network in the environment and compute rewards;  
4. Perform selection, crossover, and mutation;  
5. Save the best network and generate visualizations.  

---

## 🧾 How to Run  

```bash
# Clone repository
git clone https://github.com/renleyun7/ESP-RNN-evolution.git
cd ESP-RNN-evolution

# Install dependencies
pip install gymnasium[box2d] numpy matplotlib networkx

# Run main script
python main.py
```

You can also open the `.ipynb` file in **Google Colab** and execute all cells directly.  

---
