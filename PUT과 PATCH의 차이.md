둘 다 데이터를 수정할 때 쓰는 메서드입니다. 그러나 다음과 같은 차이가 있습니다.

### PUT 
업데이트하는 데이터의 전체를 보내다. 요청을 보낼 때 해당 데이터 전체를 보내야 하고 전체 데이터의 교체를 의미합니다.
또한, PUT은 만약 해당 데이터가 없다면 새로이 생성하고 있다면 해당 데이터가 있다면 요청할 때 보낸 데이터와 교체를 진행합니다.
예를 들어 '{"a" : 1, "b" : 2}'가 있을 때 b를 3으로 바꾼다고 했을 때 'put'의 경우 '{"a" : 1, "b" : 3}'으로 전체 데이터 전부를 보내야 합니다.

### PATCH 
업데이트하는 데이터의 일부를 보내다.
요청을 보낼 때 수정하는 일부분만 보내면 되고 일부분의 교체를 의미합니다.
예를 들어 '{"a" : 1, "b" : 2}'가 있을 때 b를 3으로 바꾼다고 했을 때 'patch'는 '{"b" : 3}' 이런 식으로 부분적으로 보내는 것을 말합니다.
