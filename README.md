# auto_car_experience_training
This is for Reinforcement Learning course project. Based on "Using Keras and Deep Deterministic Policy Gradient to play TORCS".
At the original version, the training time is longer and not stable. We made some changes that adding experience training (learning from drive example) before RL process.


--------------
## Using Keras and Deep Deterministic Policy Gradient to play TORCS

300 lines of python code to demonstrate DDPG with Keras

Please read the following blog for details. The first blog is written by original author and the second one is written by our team.

https://yanpanlau.github.io/2016/10/11/Torcs-Keras.html

https://github.com/QiyuZ/auto_car_experience_training/blob/master/Apprenticeship%20Learning%20Based%20onDeep%20Deterministic%20Policy%20Gradientsfor%20Autonomous%20Driving.pdf

## Installation Dependencies:

* Python 2.7
* Keras 1.1.0
* Tensorflow r0.10
* [gym_torcs](https://github.com/ugo-nama-kun/gym_torcs)

## How to Run?

```
git clone https://github.com/yanpanlau/DDPG-Keras-Torcs.git
cd DDPG-Keras-Torcs
cp *.* ~/gym_torcs
cd ~/gym_torcs
python pre_train.py
python ddpg.py 
```

(keep the flag **train_indicator**=0 in ddpg.py if you want to use our method)


## Tips
- Notice this project is based on Ubuntu system. Although it could work at VM I highly recommand you to use a "real" Ubuntu to make the training quicker
- It's important to run this project with fixed version of dependencies or closest. Please don't use a new version
- For the gym_torcs installation. Please enter https://github.com/ugo-nama-kun/gym_torcs and follow each step carefully. Someone may have error when "make". If so, swtich line 64 in gym_torcs/vtorcs-RL-color/src/modules/simu/simuv2/simu.cpp to 

    ```if (isnan((float)(car->ctrl->gear)) || isinf(((float)(car->ctrl->gear)))) car->ctrl->gear = 0;```
- "torcs" in terminal to make sure your simulator could work.
- If it's still to slow to train. You could also change a simple map. From some issues in the original project, it may never converge if the map is too complex or your pc is not powerful
- Remember to delete the trained model (the file ended with .jason and .h5) if you want to train a new model. If not, it will be trained quicker in the beginning. However, after several times, it may overfit.
- Welcome to tell me your question or your improvment :)
