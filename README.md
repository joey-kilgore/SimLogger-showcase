# SimLogger-showcase
Showcase of SimLogger for GW OSS Award

# installation
Always good practice to have virtual environments
Then you can pip install easily!

```
virtualenv venv
source venv/bin/activate
pip install SimLogger
```

# Using SimLogger
SimLogger actually has 3 submodules each designed
to help scientific simulations in distinct ways
1. SimLogger.SimLogger - data logging
2. SimLogger.FigLogger - cloud save for figures
3. SimLogger.SimNotify - remote notifications

## SimLogger.SimLogger Example
Watch ./data/obj and example.log

The basics:
```
SimLogger.SimLogger.logNotes(notes)

SimLogger.SimLogger.saveObj(simTag, 
                            objTag, 
                            obj, 
                            objFolder='data/obj', 
                            makeNote=False)

SimLogger.SimLogger.getObjectFromUniqueId(uniqueId, 
                                objFolder='data/obj')
```

## SimLogger.SimNotify Example
Channel - https://notify.run/c/w6gjghJKPptXnttInhj2

```
endpoint = "https://notify.run/c/w6gjghJKPptXnttInhj2"
SimNotify.sendNotification("Hello World", endpoint)
```

## SimLogger.FigLogger Example
You will need to run `kachery-cloud-init` to install
and setup your machine with the cloud service

```
t = [0,1,2,3]
cpu_temp = [30,30,100,100]
SimLogger.FigLogger.createPlot(simTag, 
    objTag, 
    x, 
    y, 
    objFolder='data/obj', 
    z=None, 
    plotType='scatter', 
    title='Plot', 
    labels={'x': 'x', 'y': 'y', 'z': 'z'}, 
    makeNote=True, **kwargs)
```
