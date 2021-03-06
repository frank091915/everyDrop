<template>
  <div class="hello">
  </div>
</template>

<script>
export default {
  name: 'jsFundation',
  methods: {
    circleFunction(){
      // for(var i = 0;i < 25; i++){
      //   console.log(i)
      // }

      // 1、还可以这样写
        // var i = 0;
        // for(;i < 25;){
        //   console.log(i)
        //   i++
        // }

      // 2、和while相似
        // while(i < 25){
        //   console.log(i)
        //   i++
        // }

      ///3、continue作用，不是继续，是进入下一轮循环，性能优化
        // for(var i = 0;i < 100;i++){
        //   if((i % 7) === 0 || (i % 10) === 7){
        //     continue
        //   }
        //   console.log(i)
        // }

      // 4、(1)小括号中不能写比较语句
      //    (2)大括号里面不能写递增、递减
        // var i = 100;
        // for(;i--;){
        //   console.log(i)
        // }

      // 5、100以内的质数,仅内被1和自己整除的数
        var result = true
        // result需要设为true,判断条件是能被其他数整除，result变为false,如果第一个数刚好不能被其他数整除，但result最终为false,该数会给判断为不是质数，所以第一个数未被错误判断
        for(var i = 3; i < 100; i++){
          for(var j = 1; j < i; j++){
            if(j !== 1 && i%j === 0 && j !== i){
              result = false
              break
              // 可以被其他数整除，直接判断不是质数，停止后续的循环判断
            }
          }
          if(result){
            console.log(i + '是质数')
          }else{
            console.log(i + '不是质数')
          }
          result = true
        }

      // 6、typeof
        // typeof(null) 返回object,null表示空对象指针 ,历史遗留错误
        // typeof(array) 返回object
        // typeof('1' - 1) 返回number
        // type(未定义a)返回undefined reference error
        // typeof(type(未定义a)) 返回string
        // typeof(+) 报错syntaxError

      // 7、显示类型转换
        // 1、Number 用于任何类型数值转换
          // Number() => number or NaN
          // Number([], null ,false) 都返回0; Number({}, undefined) => NaN
            // typeof([], null)同样返回object
          // isNaN(a),转换参数为number,如果能转换为number,返回false,否则返回true
          // ！isNaN([]、null) => false ; isNaN({}、undefined) => true

        // 2、parseInt;parseFloat 用于字符串类型数值转换
          // parseInt(只有字符串数字能转换为number)，其他的都转换为NaN
          // parseInt('b', 16) => 11
          // parseInt(13.14) => 13 只取int部分
          // 第二个参数为，进制数(2 ~ 36)
          // parseInt('123abc') => 123
          // parseInt('abc123') => NaN parseInt从开头判断，遇到数字就开始转换，非数字就停止，开头为非数字，直接返回NaN
        // 3、nunberObject.toFixed(2) 四舍五入保留指定位数小数值
          // 3.14.toFixed(1) => 3.1

      // 8、隐式类型转换
        // 1、递增、递减运算符
          // var a = '123'
          // console.log(++a) => 124
        // 2、含有字符串的 + 运算,数值会先转换为字符串 String()
          // console.log('123' + 1) => '123' + String(1) => '1231'
        // 3、* 、%、/、- 乘、除、模、减  会先转换为number Number()
          // console.log('3' * 2) => 6 Number('3') * 2
        // 4、比较运算、不全等相等运算都会转换为number再进行比较
          // (1) console.log(2 > '5') => false
            // 如果是两个字符串比较，则从左到右比较对应的ASCII码 0-9 < A-Z < a-z
            //'adc' > 'ABC'
          // (2) NaN与所有其他值的比较、相等运算都返回false(涉及到NaN的操作都会返回false)
            // 有个有趣的现象
            // NaN > 3 => false
            // NaN <= 3 => false
          // (3) 2>1>3 => false
          // (4)undefined != 0 null!= 0 
            // undefined == null undefined派生于null
        // 5、- 和 + 符号转换,转换成number
          // var a = '123'
          // console.log(-a, +a) => -123;123
    }
  },
  mounted() {
    this.circleFunction()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
</style>
