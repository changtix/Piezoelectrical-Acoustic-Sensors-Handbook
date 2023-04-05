## Kalman Filter

source for the equations: [Mithi, Sensor Fusion and Object Tracking using an Extended Kalman Filter Algorithm — Part 1 ](https://medium.com/@mithi/object-tracking-and-fusing-sensor-measurements-using-the-extended-kalman-filter-algorithm-part-1-f2158ef1e4f0) </br>
**Predict** </br>
 &ensp; Predict (a priori) state estimate: $\mathbf{\hat x}\_{k|k-1} = \mathbf{F}\_{k} \mathbf{\hat{x}}\_{k-1|k-1} + \mathbf{B}\_{k} \mathbf{u}\_{k}$ </br>
 &ensp; Predict (a priori) state estimate coveriance: $\mathbf{P}\_{k|k-1} = \mathbf{F}\_{k} \mathbf{P}\_{k-1|k-1} \mathbf{F}\_{k}^T + \mathbf{Q}\_{k}$ </br>
**Update** </br>
 &ensp; Innovation or measurement residual: $\mathbf{\tilde{y}}\_k = \mathbf{z}\_k - \mathbf{H}\_k \mathbf{\hat x}\_{k|k-1}$ </br>
 &ensp; Innovation (or residual) covariance: $\mathbf{S}\_{k} = \mathbf{H}\_{k} \mathbf{P}\_{k|k-1} \mathbf{H}\_{k}^T + \mathbf{R}\_{k}$</br>
 &ensp; Optimal Kalman Gain: $\mathbf{K}\_k = \mathbf{P}\_{k|k-1} \mathbf{H}\_{k}^T \mathbf{S}\_{k}^{-1}$</br>
 &ensp; Updated (a posteriori) state estimate: $\mathbf{\hat x}\_{k|k} = \mathbf{\hat x}\_{k|k-1} + \mathbf{K}\_k \mathbf{\tilde{y}}\_k$</br>
 &ensp; Updated (a posteriori) estimate covariance: $\mathbf{P}\_{k|k} = (\mathbf{I} - \mathbf{K}\_k \mathbf{H}\_{k})\mathbf{P}\_{k|k-1}$</br>