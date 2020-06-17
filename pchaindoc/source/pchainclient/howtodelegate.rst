===============
How to Delegate
===============

Pchain have 12 epochs per year, and in each epoch there are 4 phases. You can delegate during the first phase.

+------------+--------------------------------------+------------------------------+
| Phase      | Block Number                         | What you can do              | 
+============+======================================+==============================+
| 0% ~ 75%   | start_block ~ vote_start_block - 1   | apply candidates and delegate| 
+------------+--------------------------------------+------------------------------+
| 75% ~ 85%  | vote_start_block ~ vote_end_block    | vote                         |
+------------+--------------------------------------+------------------------------+
| 85% ~ 95%  | reveal_start_block ~ reveal_end_block| reveal vote                  |
+------------+--------------------------------------+------------------------------+
| 95% ~ 100% | reveal_end_block + 1 ~ end_block     | check next epoch's info      |
+------------+--------------------------------------+------------------------------+

You can check the current stage by our `Monitor <https://monitor.pchain.org>`_, our by RPC `tdm_getEpoch <https://github.com/pchain-org/pchain/wiki/JSON-RPC#tdm_getEpoch>`_.



>>>>>>>>>>>>>>>>>>>>>
Delegate
>>>>>>>>>>>>>>>>>>>>>

You can delegate by RPC `del_delegate <https://github.com/pchain-org/pchain/wiki/JSON-RPC#del_delegate>`_.
::
	curl -X POST -H "Content-Type:application/json" --data '{"jsonrpc":"2.0","method":"del_delegate","params":["your address","candidates address", "amount you wanna delegate"],"id":1}' localhost:6969/chainid

.. _Client Cancel Delegation:

>>>>>>>>>>>>>>>>>>>>>
Cancel Delegation
>>>>>>>>>>>>>>>>>>>>>

1) If your candidate is validator in current Epoch, the cancelation will be effective immediately. Your PI will be automatically unlocked to your balance when the current Epoch reaches 100%.

2) If your candidate is not validator in current Epoch, then the cancelation will take effect immediately and your PI will be automatically unlocked to your balance.


You can cancel delegation by RPC `del_canceldelegate <https://github.com/pchain-org/pchain/wiki/JSON-RPC#del_canceldelegate>`_.
::
	curl -X POST -H "Content-Type:application/json" --data '{"jsonrpc":"2.0","method":"del_cancelDelegate","params":["your address","candidates address", "amount you wanna withdraw"],"id":1}' localhost:6969/chainid