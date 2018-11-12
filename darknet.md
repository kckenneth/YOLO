# Darknet

<a href=https://github.com/kckenneth/YOLO/blob/master/setup_docker.md><<Previous Docker setup</a>

```
# docker run --rm -ti darknet bash
```
Once we're in the container, run the following to check the dog, horse and person images. 
```
# cd /darknet
# ./darknet detect cfg/yolov3.cfg yolov3.weights data/dog.jpg
# ./darknet detect cfg/yolov3.cfg yolov3.weights data/horses.jpg
# ./darknet detect cfg/yolov3.cfg yolov3.weights data/person.jpg
```

## Results
For dog image
```
Loading weights from yolov3.weights...Done!
data/dog.jpg: Predicted in 29.806422 seconds.
dog: 100%
truck: 92%
bicycle: 99%
```

For horses image
```
Loading weights from yolov3.weights...Done!
data/horses.jpg: Predicted in 30.402975 seconds.
horse: 100%
horse: 100%
horse: 96%
horse: 95%
```

For person image
```
Loading weights from yolov3.weights...Done!
data/person.jpg: Predicted in 30.276133 seconds.
horse: 100%
dog: 99%
person: 100%
```

