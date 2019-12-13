# Code-Tricks

1. How to use LiveData
```
val viewStateLive: LiveData<AsteroidViewState>
        get() = viewStateMutableLive
        
private val viewStateMutableLive by lazy { MutableLiveData<AsteroidViewState>() }
```
