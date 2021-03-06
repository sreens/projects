%% Sameet Sreenivasan August 2014

Plotto serves up a list of IMDb action movie plot-keywords based on the user-provided length of the list, and user parameters indicating the frequency of random choice of keyword, and the frequency with which previously seen (i.e. having appeared in existing movies) combinations of keywords appear. 

TO RUN:
At command line type: python Plotto.py


DESCRIPTION:
Plotto uses a reduced graph/network between keywords. This graph is obtained from the weighted network between all keywords appearing in all US produced action movies in the English Language. From this weighted network we obtain (using association network analysis) a forest of hierarchical trees where each tree represents a distinct thematic hierarchy. For example, a given tree may have "time-travel" as its root keyword, and in the generation below have keywords "portal", "grandfather-paradox" etc. and so on.  Once we have this forest, we extract all the root keywords. These represent the most high level plot-themes appearing in the dataset. 

Next, we obtain the induced subgraph/ sub-network between these root keywords, and uses it as the engine that drives Plotto. 

One more step is the partitioning of this subgraph into "communities" or "clusters" which are indicative of groups of keywords appearing more often together. When both random choice or a repeat combination producing choice are rejected, the algorithm first picks a random keyword in the list produced so far, notes its "community", and then picks a random keyword from one of the other communities.