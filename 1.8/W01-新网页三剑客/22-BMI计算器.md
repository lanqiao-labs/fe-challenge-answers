```html
function cal() {
    var cm = document.querySelector("#cm_input").value
    var kg = document.querySelector("#kg_input").value
    document.querySelector("#bmi_result").innerHTML = cal_bmi(cm, kg).toFixed(2)
    document.querySelector("#weight_status").innerHTML = weight_status(cm, kg)
}

function cal_bmi(cm, kg) {
    // TODO:完成计算BMI的函数,并返回BMI值 BMI = kg / (cm * cm / 10000)
    return kg / (cm * cm / 10000)
}

function weight_status(cm, kg) {
    // TODO:根据BMI值判断体重状态,并返回相应的文字描述
    // 参考值：BMI值≤18.5：过轻；18.5-24.9：正常；25-29.9：过重；30：肥胖
    // 体重状态：过轻、正常、过重、肥胖
    var bmi = cal_bmi(cm, kg)
    if (bmi <= 18.5) {
        return "过轻"
    }
    else if (bmi <= 24.9) {
        return "正常"
    }
    else if (bmi <= 29.9) {
        return "过重"
    }
    else {
        return "肥胖"
    }
}



```