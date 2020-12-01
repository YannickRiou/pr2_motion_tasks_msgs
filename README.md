# pr2_motion_tasks_msgs

# Plan action server
## goal
action -> pick, place, move, drop  
boxId: for the place, to specify in which box should be placed the object  
objId: Id of the object that has to be used for the action *pick* (not mandatory for the other actions but better to have it for fact handling)  
planGroup: group of joints to use for an action, has to be used for the actions *place* and *drop* -> left_arm, right_arm  
pose: has to be used for the *move* action  
predefined_pose_id: has to be used for the *move* action instead of pose -> right_arm_home, left_arm_home  

## result
### Error codes
1: Success  
-1:	Planning of the task failed   
-4:	Update of the world failed (no transform between map and base_footprint)  
-5:	Update of the world failed (failed to get meshes from ontologenius)  
-6:	Update of the world failed (failed to get poses from underworld service)  
