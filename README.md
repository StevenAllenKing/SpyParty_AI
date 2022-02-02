## an AI agent to play Spyparty

- Components
    1. Screen to map locations - Yolo_v5
        - from a given frame, find centroid of party member's bounding box
        - given the camera position and location of centroid, place party member on map of party
            - https://medium.com/blueeye-ai/use-yolo-v5-for-social-distancing-ff28bdd4fd08
            - Assume every person is standing in the same flat. First, we get center-bottom point of the bounding box and convert (x, y) points to bird’s eye view.
            - Second, we define the limit distance (ex: the distance between two blue points is 2 meters) corresponding to width, height of RoI, and convert these blue points to bird’s eye view.

    2. Identify party member and animation state
        - retrain Yolo_v5 on spyparty classes
    3. create graph of party member locations/activities with time stamps
    4. predict character roles and probablility of spy identification
    5. Train RL agent to control sniper laser, optimizing for the spy identification.
