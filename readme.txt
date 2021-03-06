Deal-Init
Roll20 API Script to Deal Initiative for Savage Worlds Games

DealInit supports Savage Worlds style card based inititive by dealing cards to the Turn Order and sorting the order by suit.

It does not, however, utilize the Roll20 deck system. Instead it manages an internal array of cards that are reshuffled when the deck runs out or a joker is drawn.

It also checks character attributes for any SW Inititative Edges and handles them appropriately.  The Initiative Edges must be stored in a comma separated list in an Attribute named "InitEdges" (e.g. Qui,LH)

The Edge shorthand is as follows: (spelling and case count!)
  Qui = Quick
  LH  = Level Headed
  ILH = Improved Level Headed
  WCE = Any Joker Activated Wild Card Edge (announced in turn order)

Going on Hold is accomplished by the GM editing the affected token's card to be "H" or "h."  As long as the card is an H/h, DealInit will not deal a card to that token and will put it at the top of the order on a new round.  The GM must set the card to an non-H/h value in order for DealInit to start dealing to that token again.

The script only has a few options:

!deal-init [ --help ] [--reset ] [ --show ] [ --onlyto --string ]
(no args) Deals cards to turn order and sorts by suit.
--help : Displays the help.
--reset : Reset the deck and shuffle. Use at the start of a new scene or encounter to start the deck fresh
--show : Shows the current contents of the deck, discard pile, and turn order (hand)
--onlyto --string : Deal initiative only to token names that contain "string".  Overwrites init if token is on hold. Case sensitive.


I personally use 3 macros to call the script that look like this:
"New Scene"
!deal-init --reset
!deal-init

"New Round"
!deal-init

"Deal Only To"
!deal-init --onlyto --?{Enter name to deal to|string}



