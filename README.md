Reservoir Computing
-----------------------------------------
- It's a machine learning method for processing temporal data
- Instead of training all network weights, only the "output layer" is trained
- The "reservoir" (or feature vector in NG-RC) processes input in a fixed, complex way
- NG-RC replaces the traditional reservoir with a fixed transformation of delayed inputs
- This makes it more predictable and mathematically tractable than traditional RC

>Nonlinear Vector Autoregressive (NVAR) - it's a math base of Reservoir Computing with time delays for oscillator forecasting.

Next-Generation Reservoir Computing (NG-RC)
----------------------------------------
• Replaces the reservoir with delay coordinates and polynomial features
• More predictable and mathematically tractable
• Uses time-delayed inputs as the 'reservoir'
• Creates nonlinear features from the delayed inputs

How NG-RC Works 
----------------------------------------
1. DELAY EMBEDDING: Creates feature vector using past values:
   [x(t), x(t-τ), x(t-2τ), ...] where x is the 2D state vector [pos, vel]
2. POLYNOMIAL FEATURES: Creates nonlinear combinations:
   [linear terms, quadratic terms, cubic terms, ...]
3. TRAINING: Uses ridge regression to learn output weights
4. PREDICTION: Uses learned weights to forecast future states
5. ANALYSIS: Compares predicted vs true fixed points of the system



>Key insight: The delay coordinates [x(t), x(t-τ), x(t-2τ), ...] form an embedding that preserves the essential topology of the original multi-dimensional phase space.


NG-RC replaces this complex reservoir with a simple but mathematically principled approach:

Instead of random recurrent connections → Use delay taps (explicit time history)
Instead of nonlinear reservoir activation → Use polynomial combinations of delay taps


Key Parameters in This Implementation:
----------------------------------------
• Input dimension (d): 2 (2D oscillator: position, velocity)
• Delay taps (k): 2 (using current and 1 past value)
• Polynomial degree: 3 (cubic features)
• Total features: 4 linear + 20 nonlinear = 24 total
• Ridge parameter: 0.001 (controls regularization)


# Citation

One of the best repo of Reservoir Computing
https://github.com/eloMG/Probabilistic-load-forecasting-with-Reservoir-Computing

If you use this work in your research, please cite
```
@ARTICLE{10360823,
  author={Guerra, Michele and Scardapane, Simone and Bianchi, Filippo Maria},
  journal={IEEE Access}, 
  title={Probabilistic Load Forecasting With Reservoir Computing}, 
  year={2023},
  volume={11},
  number={},
  pages={145989-146002},
  doi={10.1109/ACCESS.2023.3343467}}
```
