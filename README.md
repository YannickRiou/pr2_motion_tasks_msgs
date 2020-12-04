# pr2_motion_tasks_msgs

# Plan action server
## Pick
### goal
*objId* : name of the object to be picked

*planGroup* : arm name to be used (left_arm, right_arm). If none is specified, the arm closer to the object is chose

### result
#### Error codes
1: Success  
-1:	Planning of the task failed   
-4:	Update of the world failed (no transform between map and base_footprint)  
-5:	Update of the world failed (failed to get meshes from ontologenius)  
-6:	Update of the world failed (failed to get poses from underworld service)  

*cost*: return the cost of the planified task

*armUsed*: return the arm name (left_arm, right_arm) that is used in the task.

## Place
### goal
*objId*: name of the object to be placed (optional)

*boxId*: name of the box in which to place the object

*planGroup* : arm name to be used (left_arm, right_arm).

### result
#### Error codes
1: Success  
-1:	Planning of the task failed   
-4:	Update of the world failed (no transform between map and base_footprint)  
-5:	Update of the world failed (failed to get meshes from ontologenius)  
-6:	Update of the world failed (failed to get poses from underworld service)  

*cost*: return the cost of the planified task

*armUsed*: return the arm name (left_arm, right_arm) that is used in the task **(not useful for this task)**


## move
### goal
*pose*: a specific pose (PoseStamped ros type) to move the arm to. Mutually exclusive with predefined_pose_id.

*predefined_pose_id*: a predefined pose id (left_arm_home, etc.). Mutually exclusive with pose.

*planGroup* : arm name to be used (left_arm, right_arm).

### result
#### Error codes
1: Success  
-1:	Planning of the task failed   
-4:	Update of the world failed (no transform between map and base_footprint)  
-5:	Update of the world failed (failed to get meshes from ontologenius)  
-6:	Update of the world failed (failed to get poses from underworld service)  

*cost*: return the cost of the planified task

*armUsed*: return the arm name (left_arm, right_arm) that is used in the task. **(not useful for this task)**

## drop
### goal
*objId*: name of the object to be dropped (optional)

*planGroup* : arm to be used for the drop

### result
#### Error codes
1: Success  
-1:	Planning of the task failed   
-4:	Update of the world failed (no transform between map and base_footprint)  
-5:	Update of the world failed (failed to get meshes from ontologenius)  
-6:	Update of the world failed (failed to get poses from underworld service)  

cost: return the cost of the planified task

armUsed: return the arm name (left_arm, right_arm) that is used in the task. **(not useful for this task)**

### Feedback
A feedback containing a progress level as a number going from 0 to 100(%) to give info on the planning status.



# Execute action server
## goal
No goal. Last planned task will be executed.
## result
### Error codes
1: Success  
-2:	Execution of the task failed
-3:	Last planned task have no solutions

## Feedback
A feedback is returned during the execution process as an increasing number to show that the executing is still happening.
