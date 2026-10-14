
# Drone Race

## Overview

<div style="display: flex; align-items: flex-start; gap: 1.5rem; flex-wrap: wrap;">
<div style="flex: 1; min-width: 200px;">
Your task is to develop controllers for autonomous quadrotor flight through gate-based tracks. You will first test your controllers in simulation, then deploy them onto Crazyflie hardware. At the end of the semester, you will compete for the fastest times.
</div>
<img src="/ece484-site/assets/images/quadrotor-sketch.png" alt="Quadrotor drone" style="max-width: 200px; border-radius: 6px; flex-shrink: 0;">
</div>

## Simulation
Develop <u>both an attitude-based and a state-based controller.</u> Test them in simulation. 

You will be provided basic tracks. In your final evaluation, your controllers will be stress-tested on hidden test cases/tracks. <u>It is your job to verify the robustness of your controller.</u> 

In addition to gates, hidden test, the hidden test cases/tracks may involve the following challenges: 

- Randomized start pose 
- Tight turns
- Stationary obstacles
- Steady wind and gusting
- Impulse forces that mimic a collision
- Battery sag that reduces available thrust over a run
- Motor imbalances that pull the drone off its commanded attitude

NOTE: You are eligible to begin the hardware deployment stage once you demonstrate successful simulation runs on the basic tracks. 

## Hardware Deployment
Deploy your controllers onto Crazyflie hardware and test them in the flying arena. <u>Note that for hardware deployment, you must implement a kill switch and a stale pose watchdog.</u> More information on those in the repository README.

<u>You may deploy any controller of your choice.</u> You can use the ones from simulation, or develop an entirely new controller. A camera is available upon request if you choose to implement a vision-based controller. 

Hardware deployment has two stages:

- **Preliminary:** Achieve sim-to-real transfer on the basic tracks.
- **Race preparation:** Upon completion of the preliminary stage, you will be given the final race track. Your task is to optimize and further develop your controller to meet the minimum race requirements and compete against other groups. 

## Technical Stack

You will be provided with the necessary hardware and the following software stack: 

| Component | Description |
|-----------|-------------|
| **crazyflow** | MuJoCo MJX / JAX simulator with Gymnasium interface, four drone physics models, vectorized environments, and configurable disturbances and randomization |
| **Controller interface** | Base `Controller` class with state (position/velocity/acceleration) and attitude command modes |
| **Track configs** | TOML track definitions (gates, obstacles, start pose, disturbances), a random track generator, and a script to capture real tracks from motion capture |
| **Deployment tools** | Motion-capture tracking, state estimation, and a deploy script that runs your controller on Crazyflie |

## Important Dates and Grading

| Date | Category | Weight |
| --- | --- | --- | 
| Week of 10/19 | Project Pitch | 10% | 
| Week of 11/16 | Check-in | 20% | 
| Week of 11/30 | Final evaluation | 30% |
| 12/11 | Final presentation | 40% |

For the final evaluation, <u>the simulation code is due on 12/4.</u> The final race demo can be done in any available time slot in the week of 11/30. 

#### Project Pitch
Your pitch should contain the following at minimum: 

- Problem statement
- Preliminary simulation results
- Planned work for simulation and hardware deployment 

| Weight | Task | 
| --- | --- |
| 5% | Website is published |
| 5% | Pitch contains the required content |

#### Check-in
| Weight | Task |
| --- | --- |
| 5% | Demo successful simulation on basic tracks |
| 5% | Demo successful hardware deployment on a basic track |
| 10% | Individual quiz (oral, in-person). Anything relevant to the project up to that point is fair game. |

You may do the two demos before the week of 11/16 if you feel ready. 

#### Final evaluation
| Weight | Task |
| --- | --- |
| 15% | Simulation stress-test |
| 15% | Final race |

**Simulation stress-test**

To receive full credit, your submitted simulation controllers must pass all of the hidden test cases/tracks. Passing a test case means completing 5 laps without collisions. No time limit will be enforced.

**Final Race**

To receive full credit, your drone must complete 5 laps of the race track within the time limit with no collisions. The race track will be provided to you once the [preliminary stage](#hardware-deployment) is completed.

<u>MORE DETAILS TBA.</u>

## Primary Mentors

Vishesh and JD

## Questions

Please direct all questions to the project Slack (link on CampusWire).

## References

The repository below will have an update on 10/14. 
[Repository](https://github.com/safeautonomy-illinois-students/fa26-drone-track-release)
