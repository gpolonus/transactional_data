# StackTrack

## Lexicon

`stack`
- essentially an account
- more specifically a collection of substacks

`substack`
- category of money
- essentially a bucket
- contains money put into it via 'moves'
- money also leaves via 'moves'

`move`
- money is put into a substack via moves
- when a move has no source move, it is money entering the system
- each move has only one source move
- 'source move' is stored so that money can be accurately tracked through the system
- moves cannot move more money than is in the source move of the move
    - this means that moving an amount that is larger than any single source move of a substack requires multiple moves

`source move`
- the move that put money into a substack before it was moved out of a substack

`transaction`
- collection of moves
- mostly for UI purposes of nicely showing how money moves through the system


## Functionality

### MVP

Money enters a stack and substack via a move

When money leaves a stack, data is recorded to track what substacks in that stack were decreased to allow for that leaving

so if a transaction is for large amount of money, you know exactly where that money is coming from

when making a transaction, the system will recommend where the money should come from based on sizes of substacks
but the user can change how much is taken out of whichever substacks
ensure that all the numbers line up between substacks depleted and amount exiting the stack

movements from a substack to another substack in the same stack are allowed
these transactions offer the same amount of data as other transactions


## Mockups
_These will be look and feels of the different views without any regard to them being filled with real data_
_can use well designed components or not, I don't care_

### Views

- all stacks
- where is my money going?
- where did this money come from?

#### Mutations

- create stack
    - cannot create a stack with money in it
    - can establish a stack as 
- create transaction
    - allow for movement from several substacks in one stack to one substack in another stack
- click and drag one substack onto another substack to start a transaction


## Implementation

Graph database? 

Svelte for FE
sveltekit?

Database query abstraction layer that includes caching and creates views to the data

built from project template
project template includes
- svelte
    - components
- express
    - cors
    - helmet
    - endpoint examples
    - routing examples
    - controller abstraction
- fav npm modules
- docker compose to get stuff up and running like dbs, server, etc



## Verson 2

user specific data

credit cards should be able to work within this system
transactions can go from many substacks in a stack to many substacks in a stack

stacks can have rules attached to them
- interest rates, etc

RECURRING TRANSACTIONS
- transactions that repeat on a certain basis
    - x number of monthly
    - x number of yearly
    - x number of weekly
    - x number of daily
    - every certain day of the month
    - every certain day of the week
    - day closest to a certain day of the month not on a weekend
    - etc

labels
- might be useful to have a label system so that it's easy to aggregate where money is going
- could be labeling of stack or substacks
- maybe someone could create a stack for substacks that all belong together

goals
- substacks need a to contain a certain amount of money by a certain time
- per money that is scheduled out of my account, how am I doing?


## Version X

Query language for the data

custom data visualizations

really good caching system
