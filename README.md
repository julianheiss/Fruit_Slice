# Fruit Slice

## Table of Contents

1. [Introduction](#introduction)
2. [Preperation](#preperation) -[Protess Preperations](#prozess-preperations) -[CPEE](#cpee)
3. [Process](#process) -[Demo Process](#demo-process) -[Graph](#graph) -[Endpoints](#endpoints) -[Data Elements](#data-elements) -[Individual Process](#individual-process) -[Graph](#graph-1) -[Endpoints](#endpoints-1) -[Data Elements](#data-elements-1)

## Introduction

Every beautiful cocktail needs decoration. The robot therefore places a slice of lime on the edge of a glass.

## Preperation

### Prozess Preperations

- Glas in the "In-progress" position
- Four lime slices in the lime slice holder with the slot of each slice above the marker in the middle. Each lime slice should have a thickness of 0.9 cm to 1.3 cm.
- The finger protection shall be placed in the protection depot on the middle bar so that the longer side of the protection faces inwards (see image XYZ)
- Turn the cobot into automatic and remote

### CPEE

- Go to https://cpee.org/hub/?stage=development&dir=Teaching.dir/Prak.dir/TUM-Prak-24-SS.dir/
- Open "fruit_slice.xml" or "fruit_slice_demo.xml" depending if you want to see a demo loop or the individual process
- Start the process by clicking start in the execution tab

## Process

### Demo Process

This process is for demonstration purposes and shows a sample integration of the individual process. In this demo-scenario the process is executed four times in a row.

#### Graph

![Graph of the Fruit Slice Demo process](Screenshots/CPEE_fruit_slice_demo_graph.png)

- a1-Home Start: Moves from Home Position to the "In-Progress" glas
- Loop: Verifies that the index is smaller than the max number of fruits in the holder.
- a2-Place Slice: executes the subprocess of the "fruit_slice.xml"
  ![Subprocess](Screenshots/CPEE_fruit_slice_demo_subprocess.png)
- a3-Next Fruit Slice Index Increase: Increases the fruit_index variable by 1
- a4-Return Home: Returns to the Home Position from the "In-Progress" glas

#### Endpoints

![Endpoints of the Fruit Slice Demo Process](Screenshots/CPEE_fruit_slice_demo_endpoints.png)

#### Data Elements

![Data Elements of the Fruit Slice Demo Process](Screenshots/CPEE_fruit_slice_demo_dataElements.png)

- fruit_index: initial 0 (is increased in each loop executioon)
- no_of_fruits: maximal number of fruits in the holder -> 4

### Individual Process

#### Graph

![Graph of the Fruit Slice process](Screenshots/CPEE_fruit_slice_graph.png)

- a1-Pickup Finger Protection: Moves to the Finger Protection and picks up the protection by sliding into.
- a2-Set Index Register Value: This sets the index of the fruit slice by setting it in the register of the cobot
- a3-Pickup Fruit Slice: Picks up the FruitSlice depending on the registert value. This is done by an offset with Fruit0 as basis in the installation
- a4-Place Slice: The cobot places the slice on the edge of the "In-progress"-glas
- a5-Place Protection: The cobot places the protection in the Protection Depot. The cobot pushes the protection in the starting position.
- a6-Returns to working position: The cobot returns to the "In-Progress"- glas

#### Endpoints

![Endpoints of the Fruit Slice Process](Screenshots/CPEE_fruit_slice_endpoints.png)

#### Data Elements

![Data Elements of the Fruit Slice Process](Screenshots/CPEE_fruit_slice_dataElements.png)

- Has no created data elements, because the index is passed to this subprocess.
