#KOTLIN FILE
package com.example.firstclass

import android.support.v7.app.AppCompatActivity
import android.os.Bundle
import android.view.View
import android.widget.ImageView
import android.widget.TextView
import net.objecthunter.exp4j.ExpressionBuilder
import org.w3c.dom.Text
import kotlin.math.exp

class Calculator : AppCompatActivity() {
    lateinit var one :TextView
    lateinit var two :TextView
    lateinit var three :TextView
    lateinit var four :TextView
    lateinit var five :TextView
    lateinit var six:TextView
    lateinit var seven :TextView
    lateinit var eight :TextView
    lateinit var nine :TextView
    lateinit var zero :TextView
    lateinit var decimal :TextView
    lateinit var ac:TextView
    lateinit var equals:TextView
    lateinit var add:TextView
    lateinit var product:TextView
    lateinit var subtract:TextView
    lateinit var clear:ImageView
    lateinit var expression:TextView
    lateinit var result:TextView
    lateinit var divide:TextView
    lateinit var e:TextView
    lateinit var log:TextView


    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_calculator)
        zero =findViewById(R.id.zero)
        one =findViewById(R.id.one)
        two =findViewById(R.id.two)
        three =findViewById(R.id.three)
        four =findViewById(R.id.five)
        five =findViewById(R.id.five)
        six =findViewById(R.id.six)
        seven =findViewById(R.id.seven)
        eight =findViewById(R.id.eight)
        nine =findViewById(R.id.nine)
        equals =findViewById(R.id.equals)
        product=findViewById(R.id.product)
        add =findViewById(R.id.add)
        subtract =findViewById(R.id.subtract)
        divide =findViewById(R.id.divide)
        ac =findViewById(R.id.ac)
        e =findViewById(R.id.e)
        log =findViewById(R.id.log)
        clear=findViewById(R.id.clear)

        expression=findViewById(R.id.expression)
        result=findViewById(R.id.result)
        Appends(zero,true)
        Appends(one,true)
        Appends(two,true)
        Appends(three,true)
        Appends(four,true)
        Appends(five,true)
        Appends(six,true)
        Appends(seven,true)
        Appends(eight,true)
        Appends(nine,true)
        Appends(log,true)
        Appends(product,false)
        Appends(add,false)
        Appends(subtract,false)
        Appends(divide,false)
        Appends(decimal,true)
        ac.setOnClickListener{
            allclear()
        }
        clear.setOnClickListener{
            result.text=""
            if (expression.text.isNotEmpty()){
                expression.text=expression.text.dropLast(1)


            }

        }

equals.setOnClickListener{
    try{
var Expressions=ExpressionBuilder(expression.text.toString()).build()    /*converting the expression to string to get operable in inbuilt functions*/
        var RESULT=Expressions.evaluate() /*storing the results in a variable */
        result.text=RESULT.toString()     /*converting the result to string again to get stored in the result view*/



    }
    catch (exception: Exception ){
result.text=exception.message
    }
}


    }
    fun Appends(View:TextView,toclearornot: Boolean){
        View.setOnClickListener{
            append(View.text.toString(),toclearornot)
        }


    }
    private fun append(value:String ,toclearornot:Boolean){  /*to_be_cleared is used for result section*/
        if (result.text!="")
        {
            expression.text=""   /*as soon we click any button result section is cleared*/
        }
        if (toclearornot){
            result.text=""
            expression.append(value)   /* if we want to clear the result ,result section is made empty and the value which is clicked is added to the expression*/

        }
        else{
            expression.append(result.text)
            expression.append(value)
            result.text=""   /* if we want to use the result so as soon as a button is clicked we append the previous result into expression section */
            /*Then we append the value of the text view into expression which we clicked and then we clear the result section */
        }
    }
    private fun allclear(){
        result.text=""
        expression.text=""

    }

}
