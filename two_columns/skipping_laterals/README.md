# Skipping laterals

In progressive networks n-th layer of m-th column has lateral connections from (n-1)'th layers from all (m-1) columns. In case of our 2-column, 5-layer network it means 4 lateral connections in total. We check all possible combinations of skipping lateral connections except case of disjointing columns. This experiment might indicate what is the best way of connecting columns with lateral connections.

# Encoding

In case of 2-column progressive network:

- `xxxx` stands for all 4 connections.
- `xoxo` stands for connections from 1st and 3rd layers of first column
- `ooox` stands for one connection from 4rd layer of first column

Lateral setting | Test Accuracy in o15, lr=0.001
--- | ---
xxxx | ---
xxxo | ---
xxox | ---
xxoo | ---
xoxx | ---
xoxo | ---
xoox | ---
xooo | ---
oxxx | ---
oxxo | ---
oxox | ---
oxoo | ---
ooxx | ---
ooxo | ---
ooox | ---

Lateral setting | Test Accuracy in m15, lr=0.001
--- | ---
xxxx | ---
xxxo | ---
xxox | ---
xxoo | ---
xoxx | ---
xoxo | ---
xoox | ---
xooo | ---
oxxx | ---
oxxo | ---
oxox | ---
oxoo | ---
ooxx | ---
ooxo | ---
ooox | ---
