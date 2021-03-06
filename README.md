# Quantum Prisoner's Dilemma 

Created a non-local Quantum game using Quantum Network simulator Simulaqron, with the base of QuTip as the quantum simulator via EWL Scheme.

Quantum Game theory is based on original game theory, in which you can either deflect or cooperate, where the yield point is when one choose to deflect. However, in Quantum Game Theory, you have a continuous choice instead of binary choice, i.e you can 60% deflect and 40% cooperate, this idea extends with the use of complex number. Hence the yield point here becomes when both parties choose to 50% deflect and 50%i cooperate. 

### Description

Here alice prepares two qubits, pass them through J gate and then sents one of the qubits to Bob. Alice and Bob applies respective gates of their choice (U1, U2) without notifying the each other. Here U1 and U2 represent their quantum choices. Bob sends his qubit to Alice and Reverse J gate is applied to both of the qubits before measurement. 

### Sample test cases are as follows:

    U1  U2
	 I   I -> result should be |00>
	 I   X -> result should be |01>
	 X   I -> result should be |10>
	 X   X -> result should be |11>

Requirements
Be sure to have [SimulaQron](https://github.com/SoftwareQuTech/SimulaQron "SimulaQron") installed and running on your computer (see  guide).

### Usage

1) The decisions are hard coded for testing, though they can for sure be accepted on the go from the user.

2) After changing the decisions, the simulaqron network must be reset, else it will show unpredictable results.

It can be reset by the following command on the terminal.

	simulaqron reset 

3) Before starting simulaqron on the terminal, the backend must be changed to either projectq or qutip, as the default stabilizers do not have single qubit rotation gates.

It can be changed by the following command on terminal:

	simulaqron set backend projectq

Hence before executing and after changing the decisions, the following commands must be used.

	simulaqron reset
	simulaqron set backend projectq
	simulaqron start
	sh run.sh
