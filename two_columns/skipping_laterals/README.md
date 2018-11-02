# Skipping laterals

In progressive networks n-th layer of m-th column has lateral connections from (n-1)'th layers from all (m-1) columns. In case of our 2-column, 5-layer network it means 4 lateral connections in total. We check all possible combinations of skipping lateral connections except case of disjointing columns. This experiment might indicate what is the best way of connecting columns with lateral connections.

# Encoding

In case of 2-column progressive network:

- `xxxx` stands for all 4 connections.
- `xoxo` stands for connections from 1st and 3rd layers of first column
- `ooox` stands for one connection from 4rd layer of first column

Lateral setting | Test Accuracy in o15, lr=0.001
--- | ---
xxxx | 0.96204
xxxo | 0.96208
xxox | 0.96002
xxoo | 0.96116
xoxx | 0.95974
xoxo | 0.96058
xoox | 0.95446
xooo | 0.95536
oxxx | 0.95902
oxxo | 0.96232
oxox | 0.95906
oxoo | 0.95798
ooxx | 0.9578
ooxo | 0.95868
ooox | 0.95278

Lateral setting | Test Accuracy in m15, lr=0.001
--- | ---
xxxx | 0.4635
xxxo | 0.46604
xxox | 0.47918
xxoo | 0.47052
xoxx | 0.46382
xoxo | 0.4732
xoox | 0.46722
xooo | 0.47852
oxxx | 0.46472
oxxo | 0.472
oxox | 0.4689
oxoo | 0.4697
ooxx | 0.46596
ooxo | 0.46152
ooox | 0.46566
