# Trigger Swap Valuation

A European trigger swap is a swap that is triggered by the level of an index. For example, for a call type trigger swap, if the index is above the strike at the expiry, one counterparty receives the prescribed fixed rate. Other wise, the party receives spot swap rates.

An American trigger swap is a swap that is triggered by the level of an index at any time up to the expiration date. In order to model the problem, we assume that forward swap rate and index follow a joint lognormal distribution. Base on this assumption, a closed form solution can be derived for European trigger swaps.

However, there is no closed form solution available for American trigger swaps. In this case, a numerical approach has to be used to compute the expectation of the payoff in a risk-neutral world. In particular, we use a 3-D tree approach to price American and Bermudan trigger swaps.

There are four types of trigger swaps as follows:
•	Call type paying: If the index is above the strike, the owner enters a swap in which he pays a predefined rate and receives a floating rate.
•	Call type receiving: If the index is above the strike, the owner enters a swap in which he receives a predefined rate and pays a floating rate.
•	Put type paying: If the index is below the strike, the owner enters a swap in which he pays a predefined rate and receives a floating rate.
•	Put type Receiving: If the index is below the strike, the owner enters a swap in which he receives a predefined rate and pays a floating rate.

Our model takes the following factors into account:
•	Implied swap rate volatility term structure has been considered.
•	Implied Libor rate volatility term structure has been considered.
•	Correlation between Libor rates and remaining swap rate has been considered.

We notice that a constant correlation between the Libor rate and swap rates does note reflect the reality. As the time goes to the maturity, the remaining swap rate goes to the Libor rate, which implies that the correlation goes to 1. 

The trigger swap also has a knock-in feature with a single barrier (see https://finpricing.com/lib/EqBarrier.html). The stability of a naïve tree approach can be quickly deteriorated in cases of products with knock-in or knock-out features. To get a relatively more stable tree approach, a “smoothing edge out” technique is applied.

Our test results show that the 3-D tree approach is stable for American trigger swaps. However, the same approach for Bermudan trigger swaps is not as stable as that of American trigger swaps, but is still acceptable. 

