.. _CHALLENGES:

==================
Agility Challenges
==================

ARIAC 2025 incorporates challenges in order to test the robustness of competitors systems. Competitors should be able to acknowledge that a challenges
is occuring and properly handle the given challenge. There are four possible challenges that can occur during a run:

.. container::

    * Conveyor Malfunction
    * Voltage Tester Malfunction
    * Vacuum Tool Malfunction
    * High Priority Order

Conveyor Malfunction
====================

When the conveyor malfunction challenge occurs, the inspection conveyor will pause its motion. In addition, the cell feed will pause,
so no new cells can be added during the challenge. In order to handle this challenge, competitors will be expected to:

.. container::

    1. Know that the conveyor is malfunctioning by observing the conveyor topic, found :ref:`here <inspection_challenge_anchor>`
    2. Pause the inspection system
    3. Wait for that status topic to publish operational
    4. Once the conveyor and cell feed resume, start inspection system once agvstations_msg

Voltage Tester Malfunction
==========================

When the voltage tester malfunction occurs, one or both voltage testers will publish no data. In order to properly handle this 
challenge, competitors will be expected to:

.. container::

    1. Know that a voltage tester is malfunctioning, by observing the voltage tester topics, found :ref:`here <inspection_challenge_anchor>`
    2. Pause the use of affected voltage testers
    3. Wait for status topic of affected voltage testers to be set to operational
    4. Continue using operational voltage tester, if applicable, to continue progress toward module and kit completion
    5. Once the affected voltage tester returns to operational, continue normal use of both voltage testers

Vacuum Tool Malfunction
=======================

When the vaccum tool malfunction occurs, a pre-specified vacuum gripper will fail on a grasp attempt. In order to properly handle
this challenge, competitors are expected to:

.. container::

    1. Understand that the vacuum gripper has failed to grasp its intended object, by observing the response of the grasp service, found :ref:`here <vacuum_tool_challenge_anchor>`
    2. Move the vacuum gripper tool away from the object it was attempting to grasp
    3. Attempt to re-grasp the object

High Priority Challenge
=======================

When a high priorty order is requested, there is an internal timer that is started. We expect competitors to minimize the amount
of time taken to submit this high priority kit. In order to submit this kit, competitors are expected to:

.. container::

  1. Know that a high priority order has been requested, by observing the high priority order topic, found :ref:`here <high-priority-anchor>`
  2. Switch cell feed to begin spawning NiMH cells
  3. Build a full kit using NiMH cells
  4. Move the AGV containing the NiMH kit to the shipping location
  5. Submit the high priority order with its associated order ID, found as a service :ref:`here <high-priority-anchor>`
  6. Switch cell feed back to spawning Li-ion batteries
  7. Resume normal task operation