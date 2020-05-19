# Code-Tricks

1. How to use LiveData
```
val viewStateLive: LiveData<AsteroidViewState>
        get() = viewStateMutableLive
        
private val viewStateMutableLive by lazy { MutableLiveData<AsteroidViewState>() }
```
2. Subscribe and add to Disposables

```
private fun observeViewState(viewStateEmitter: Observable<AsteroidViewState>) {
        viewStateEmitter
            .subscribeOn(Schedulers.io())
            .subscribeBy(
                onNext = { viewState -> viewStateMutableLive.postValue(viewState) },
                onError = { error -> Log.e("qwer", "error viewstate", error) }
            ).addTo(disposables)
    }
  ```
3. How to extend View in Kotlin

```
class KotlinView @JvmOverloads constructor(
        context: Context, attrs: AttributeSet? = null, defStyleAttr: Int = 0
) : View(context, attrs, defStyleAttr)
```
