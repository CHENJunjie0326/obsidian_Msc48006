<h1 style="text-align: center;">Assignment 1: Space Mission</h1>
<h4 style="text-align: center;">Name: CHEN Junjie   No.:26121205g</h4>

--- 
# Problem 1 solution  
**(a)** On Earth, the maximum mechanical energy supplied by the astronaut’s legs is equal to the increase in gravitational potential energy during the jump:  
$$E_{leg} = mg_0h \tag{1}$$  
To escape from the surface of the asteroid, the astronaut must have at least the escape energy:  
$$E_{esc} = \frac{GM_m}{R} \tag{2}$$  
where $R$ is the radius and $M$ is the radius and mass of the asteriod.  
For a uniform-density sphere:  
$$M = \frac{4}{3} \pi R^3 \rho \tag{3}$$  
Substituting (3) into (2), which is:  
$$E_{esc} = \frac{4 GM \pi R^3 \rho}{3R} = \frac{4 \pi GM R^2 \rho}{3} \tag{4}$$  
At the critical condition, the energy given by legs is equal to the escape energy:  
$$E_{leg} = E_{esc} \tag{5}$$  
Thus:  
$$
\begin{align}
mg_{0}h &= \frac{4}{3} \pi G \rho m R^2\\
g_{0}h &= \frac{4}{3} \pi G \rho R^2 \tag{6}
\end{align}
$$  
Solving for the critical radius $R_0$:  
$$R_{0} = \sqrt{\frac{3g_{0}h}{4 \pi R \rho}} \tag{7}$$  
And the critical diameter $D_0$ is:  
$$D_{0} = 2 R_{0} \tag{8}$$  
Substituting the numerical values:  
$$
\begin{align}
&R_{0} = \sqrt{\frac{3\times9.81\times0.60}{4 \pi (6.67\times10^{-11}\times5000}} \approx 2.05\times10^{3}m \\
&D_{0} = 2 R_{0} \approx 4.11km 
\end{align}
$$  
Therefore, the astronaut can escape by jumping if  
$$D < D_{0} \approx 4.1km$$  
To prevent escape, the asteroid diameter must be:  
$$D > D_{0} \approx 4.1km$$  

**(b)** At the critical radius $R_0$:  
$$R_{0} = 2.05\times10^{3}m$$  
The asteroid mass $M_{0}$ is:  
$$M = \frac{4}{3} \pi R^3 \rho = \frac{4}{3} \pi (2.05\times10^{3})^3 (5000) \approx 1.8\times10^{14}kg$$  
So the ratio of the asteroid mass to the astronaut mass $m$ is:  
$$\frac{M_{0}}{m} = \frac{1.8\times10^{14}}{91} \approx 2.0\times10^{12}$$  
Thus,  
$${M_{0}} \gg {m} $$  
---
# Problem 2 solution  
**(a)** The circular orbital velocity is:  
$$v = \sqrt{\frac{GM}{R}} \tag{1}$$  
For Earth,  
$$v_{E} = \sqrt{\frac{GM_{Sun}}{r_{E}}} = \sqrt{\frac{(6.67\times10^{-11})(1.989\times10^{30})}{149.5\times10^{9}}} \approx 29.8km/s$$  
For Mars,  
$$v_{M} = \sqrt{\frac{GM_{Sun}}{r_{M}}} = \sqrt{\frac{(6.67\times10^{-11})(1.989\times10^{30})}{227.8\times10^{9}}} \approx 24.1km/s$$  
For a Hohmann transfer between Earth’s orbit and Mars’ orbit, the transfer ellipse has perihelion at $r_E$ and aphelion at $r_M$.  
The semi-major axis $a_T$ is:  
$$a_{T} = \frac{r_{E} + r_{M}}{2} \tag{2}$$  
Substituting the numerical values,  
$$a_{T} = \frac{r_{E} + r_{M}}{2} = \frac{149.5\times10^{9} + 227.8\times10^{9}}{2} = 1.89\times10^{11}m$$  
The general orbit velocity is:  
$$v = \sqrt{GM(\frac{2}{R} - \frac{1}{a})} \tag{3}$$  
The velocity of the perihelion of the transfer ellipse is:  
$$
\begin{align}
v_{P} = \sqrt{GM_{Sun}(\frac{2}{r_E} - \frac{2}{r_{E} + r_{M}})} 
&= \sqrt{(6.67\times10^{-11})(1.989\times10^{30})(\frac{2}{149.5\times10^{9}} - \frac{2}{1.89\times10^{11}})}\\\\
v_{p} &\approx 32.7km/s
\end{align}
$$  
So the first velocity increment is:  
$$\Delta v_{T} = v_{P} - v_{E} \approx 2.9km/s $$  
As the same way, the velocity of the aphelion of the transfer ellipse is:  
$$\begin{align}
v_{A} = \sqrt{GM_{Sun}(\frac{2}{r_M} - \frac{2}{r_{E} + r_{M}})} 
&= \sqrt{(6.67\times10^{-11})(1.989\times10^{30})(\frac{2}{227.8\times10^{9}} - \frac{2}{1.89\times10^{11}})}\\\\
v_{A} &\approx 21.5km/s
\end{align}$$  
So the second velocity increment is:  
$$\Delta v_{Mars} = v_{M} - v_{A} \approx 2.6km/s $$  
The minimum total velocity increment for the two-impulse Hohmann transfer from Earth’s heliocentric orbit to Mars’ heliocentric orbit is:  
$$\Delta v_{Total} = \Delta v_{T} + \Delta v_{Mars} \tag{4}$$  
Substituting the numerical values:  
$$\Delta v_{Total} \approx 2.9 + 2.6 \approx 5.5km/s$$  
The period of the transfer ellipse is:  
$$T = 2 \pi \sqrt{\frac{a^3}{GM}} \tag{5}$$  
The Hohmann transfer corresponds to half of an elliptical orbit. Therefore, the transit time is:  
$$t_{trans} = \frac{T}{2} = \pi \sqrt{\frac{a^3}{GM}} = \pi \sqrt{\frac{(1.89\times10^{11})^{3}}{(6.67\times10^{-11})(1.989\times10^{30})}} \approx 2.24\times10^{7}s$$  
Converting to days：  
$$t_{trans} \approx 259days$$  
**(b)** When departure is from rest at Earth’s surface, the spacecraft must first overcome Earth’s gravity which is called oberth maneuver.  
The velocity increment required to enter the Hohmann transfer orbit relative to Earth’s heliocentric orbit is:  
$$\Delta v_{T} \approx 2.9km/s $$  
At the escape point, the spacecraft initially has zero velocity relative to Earth’s surface, while it already shares Earth’s heliocentric orbital velocity.  
So the hyperbolic excess velocity $v_{exc}$ relative to Earth after escaping Earth’s gravity is:  
$$v_{exc} = \Delta v_{T} $$  
For an ideal direct launch from Earth’s surface into the Hohmann transfer trajectory, the required launch velocity increment is obtained from energy conservation:  
$$\frac{1}{2}mv_{launch}^{2} - \frac{GM_{E}m}{R_{E}} = \frac{1}{2}mv_{exc}^{2} + E_{esc}\tag{6}$$  
According to the definition of the gravitational potential energy:  
$$E_{esc} = 0$$  
Assuming that the kinetic energy obtained at the time of launch is exactly sufficient to reach the escape point, then according to the law of conservation of mechanical energy, there is:  
$$\frac{1}{2}mv_{esc,E}^{2} = \frac{GM_{E}m}{R_{E}} \tag{7}$$  
The (6) can change to:  
$$v_{launch}^{2} = v_{esc,E}^{2} + v_{exc}^{2}$$  
and the escape velocity is:  
$$v_{esc,E} = \sqrt{\frac{2GM_{E}}{R_{E}}} = \sqrt{\frac{2(6.67\times10^{-11})(5.972\times10^{24})}{6.371\times10^{6}}} \approx 11.2km/s$$  
the launching velocity is:  
$$v_{launch} = \sqrt{v_{esc,E}^{2} + v_{exc}^{2}} = \sqrt{11.2^2 + 2.9^2} \approx 11.6km/s$$  
To complete the transfer into Mars’ heliocentric circular orbit, the second impulse at Mars is still required:  
$$\Delta v_{Mars} \approx 2.6km/s $$  
Therefore, the corresponding total velocity increment from rest at Earth’s surface to Mars’ heliocentric orbit is:  
$$\Delta v_{Total,Oberth} = v_{launch} + \Delta v_{Mars} \tag{8}$$  
Substituting the numerical values:  
$$\Delta v_{Total,Oberth} \approx 11.6 + 2.6 \approx 14.2km/s$$  