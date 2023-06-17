# wildebeest_herds
COMSOL Multiphysics code for Hueschen, Dunn, Phillips, "Wildebeest herds on rolling hills: flocking on arbitrary curved surfaces"

Text is available at https://arxiv.org/abs/2206.01271. 

In the manuscript, we present a formulation of the Toner-Tu flocking theory that uses the finite element method to solve the governing equations on arbitrary curved surfaces. First, we test the developed formalism and its numerical implementation in channel flow with scattering obstacles and on cylindrical and spherical surfaces, comparing our results to analytical solutions. We then progress to surfaces with arbitrary curvature, moving beyond previously accessible problems to explore herding behavior on a variety of landscapes. This approach allows the investigation of transients and dynamic solutions not revealed by analytic methods. It also enables versatile incorporation of new geometries and boundary conditions and efficient sweeps of parameter space.

We hope that others will find our approach user-friendly and adaptable for solving the Toner-Tu equations on other complex curved surfaces, for solving other continuum equations on curved surfaces, or for additional study of the cases presented here. While we chose COMSOL Multiphysics for its accessibility and learner-friendly interface, we note with regret that the use of these files requires access to a paid COMSOL Multiphysics license. If you do not already have a license and are affiliated with an institution, we recommend looking into access options through a shared software library.

For more details and context, the section titled "Formulating the Surface Toner-Tu Equations for Numerical Implementation" in the main text and the sections titled "Implementation in COMSOL Multiphysics" and "Using and Adapting our COMSOL Multiphysics Simulations" in the appendix may be particularly useful. 

Files available in this repository:

1. Toner-Tu herding in a 2D channel with an obstacle and periodic boundary conditions. This file is a good starting place for orienting yourself to the COMSOL Multiphysics General Form PDE interface and to the 2D planar Toner-Tu equations and their syntax. To recapitulate Figure 7, remove the circular obstacle. To recapitulate Figure 8, set the obstacle radius to 15 m. To recapitulate Figure 10, set the obstacle radius to 30 m.

2. Toner-Tu herding on the cylinder. This file introduces the curved-surface implementation of the Toner-Tu equations presented in the main text section titled "Formulating the Surface Toner-Tu Equations for Numerical Implementation". Note that some important components of this formulation, such as the projection operator, can be found in 'Variables 1' under 'Definitions'. Note also that the 'Parametric Sweep' implemented within 'Study 1' explores different choices for the parameters alpha and beta, producing the results shown in Figure 10.

3. Toner-Tu herding dynamics on the sphere. This file solves the curved-surface implementation of the Toner-Tu equations, this time on a spherical geometry, and simulates the damped oscillations shown in Figure 12. Note again that some important components of this formulation are defined in 'Variables 1' under 'Definitions'. To sweep through different parameter choices for D as in Figure 13, enable `Parametric Sweep' within 'Study 1'. Remember to update plots under 'Results' and 'Exports' to reflect this new solution set ('Study 1/Parametric Solutions X').

4. Toner-Tu herding on the sphere: exploring patterns from an initial wedge confinement. This file builds on the previous one in a simple way: herd dynamics are seeded by initially confining the herd to an angular wedge, as shown in Figure 14. Tuning parameters such as sigma leads to different patterns in the long-time limit (after ~10^4 s). To recapitulate Figure 15 by sweeping through different choices for sigma, enable 'Parametric Sweep' within 'Study 1'. Remember to update 'Results' and 'Exports' to show this new solution set ('Study 1/Parametric Solutions X').

5. Herding over a hill: curvature-induced density and velocity changes at a Gaussian hill embedded in a racetrack straightaway. This file imports a racetrack with embedded hill geometry (download 'RacetrackWithHill.mphbin' and import under 'Geometry 1'). In the long-time limit, hill curvature induces the low and high density regions shown in Figure 16.

6. Herds gone wild: dynamics of a Toner-Tu herd on an undulating island landscape. This file imports an island landscape of Gaussian hills (download 'IslandOfHills.mphbin' and import under 'Geometry 1'). Herd dynamics are simulated in the absence or presence of a gravitational force with coefficient zeta, as in Figure 17.

The surface mesh geometries referenced in files 5 and 6 above ('RacetrackWithHill.mphbin' and 'IslandOfHills.mphbin') are available in the `geometries` folder.
