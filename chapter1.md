*Exercise 1.1: Self-Play* Suppose, instead of playing against a random opponent, the reinforcement learning algorithm described above played against itself, with both sides learning. What do you think would happen in this case? Would it learn a different policy for selecting moves?

Because policy learning are happening simulteneously against one another, i.e., the opponent strategy is not static, each will converge to the optimal policy against its opponent. The learnt policy would be different from the one learnt with the random opponent.

*Exercise 1.2: Symmetries* Many tic-tac toe positions appear different but are the same because of symmetries. How might we amend the learning process decribed above to take advantage of this? In what ways wolud this change improve the learning process? Now think again. Suppose the opponent did not take advantage of symmetries. In that case, should we? Is it true, then, that symmetrically equivalent positions should necessarilly have the same value?

Yes, because it reduces the state space size hence faster computation. We should still do it even the oppenent does not depends on our opponent's behaviours. Assuming they play the same strategy in all symmetrically equivalent positions, the symmetrically equivalent positions should have the same values. Otherwise, for examples, the agent always play differently on one variation of the symmetrically equivalent position, which mean we it should have a different value than the others.

*Exercise 1.3: Greedy Play* Suppose the reinforcement learning player was *greedy*, that is, it always played the move that brought it to the position that it rated the best. Might it learn to play better. or worse, than a nongreedy player? What problems might occur?

The problem is greedy does not allow exploration of new states. This would not be an issue the true value function had been learnt. It will converge to the (local) optimal in terms of the latest value function it estimated.

*Exercise 1.4: Learning from Exploration* Suppose learning updates occured after all oves, including exploratory moves. If the step-size parameter is appropriately reduced over time (but not the tendency to explore), then the state values would converge to a different set of probabilities. What (conceptually) are the two sets of probabilities computed when we do, and when we do not, learn from exploratory moves? Assuming that we do continue to make exploratory moves, which set of prbabilities might be better to learn? Which would resultr in more wins?

The one with exploration always results a lower probability values as exploration moves that results in sub-optimal performance is taken into account. As we are interested in optmising a policy with rue winning probabilities,  we should always use the set of probabilities without exploration move. This should result higher winning chance.

*Exercise 1.5: Other Improvements* Can you think of other ways to improve the reinforcement learning player?

Given the search space is small, brute force may be employed to search for the optimal policy. Alternatively, one could have seeded better intial values for position, e.g., values of middle position > corner positions > the rest of the postions, or move, if the player is the second mover with the opponent occupied the middle position, values of corner positions should be higher than non-corner positions, and/or values of non-corner positions should be zero (as they are guaranteed to lose)
