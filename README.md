### Actuary & Data Scientist 👋

# -*- coding: utf-8 -*-

# Form implementation generated from reading ui file 'financial_assets_allocation.ui'
#
# Created by: PyQt5 UI code generator 5.15.7
#
# WARNING: Any manual changes made to this file will be lost when pyuic5 is
# run again.  Do not edit this file unless you know what you are doing.


from PyQt5 import QtCore, QtGui, QtWidgets


class Ui_Dialog(object):
    def setupUi(self, Dialog):
        Dialog.setObjectName("Dialog")
        Dialog.resize(646, 262)
        self.verticalLayout_7 = QtWidgets.QVBoxLayout(Dialog)
        self.verticalLayout_7.setObjectName("verticalLayout_7")
        self.verticalLayout_6 = QtWidgets.QVBoxLayout()
        self.verticalLayout_6.setObjectName("verticalLayout_6")
        self.verticalLayout_3 = QtWidgets.QVBoxLayout()
        self.verticalLayout_3.setObjectName("verticalLayout_3")
        self.horizontalLayout = QtWidgets.QHBoxLayout()
        self.horizontalLayout.setObjectName("horizontalLayout")
        self.verticalLayout = QtWidgets.QVBoxLayout()
        self.verticalLayout.setObjectName("verticalLayout")
        self.label = QtWidgets.QLabel(Dialog)
        font = QtGui.QFont()
        font.setPointSize(10)
        self.label.setFont(font)
        self.label.setObjectName("label")
        self.verticalLayout.addWidget(self.label)
        self.label_2 = QtWidgets.QLabel(Dialog)
        font = QtGui.QFont()
        font.setPointSize(10)
        self.label_2.setFont(font)
        self.label_2.setObjectName("label_2")
        self.verticalLayout.addWidget(self.label_2)
        self.horizontalLayout.addLayout(self.verticalLayout)
        self.verticalLayout_2 = QtWidgets.QVBoxLayout()
        self.verticalLayout_2.setObjectName("verticalLayout_2")
        self.lineEditNumbersOfAssets = QtWidgets.QLineEdit(Dialog)
        self.lineEditNumbersOfAssets.setObjectName("lineEditNumbersOfAssets")
        self.verticalLayout_2.addWidget(self.lineEditNumbersOfAssets)
        self.lineEditRiskFreeRateOfReturn = QtWidgets.QLineEdit(Dialog)
        self.lineEditRiskFreeRateOfReturn.setObjectName("lineEditRiskFreeRateOfReturn")
        self.verticalLayout_2.addWidget(self.lineEditRiskFreeRateOfReturn)
        self.horizontalLayout.addLayout(self.verticalLayout_2)
        self.verticalLayout_3.addLayout(self.horizontalLayout)
        self.labelIthAsset = QtWidgets.QLabel(Dialog)
        font = QtGui.QFont()
        font.setPointSize(10)
        self.labelIthAsset.setFont(font)
        self.labelIthAsset.setObjectName("labelIthAsset")
        self.verticalLayout_3.addWidget(self.labelIthAsset)
        self.verticalLayout_6.addLayout(self.verticalLayout_3)
        self.horizontalLayout_2 = QtWidgets.QHBoxLayout()
        self.horizontalLayout_2.setObjectName("horizontalLayout_2")
        self.verticalLayout_4 = QtWidgets.QVBoxLayout()
        self.verticalLayout_4.setObjectName("verticalLayout_4")
        self.label_4 = QtWidgets.QLabel(Dialog)
        font = QtGui.QFont()
        font.setPointSize(10)
        self.label_4.setFont(font)
        self.label_4.setObjectName("label_4")
        self.verticalLayout_4.addWidget(self.label_4)
        self.label_5 = QtWidgets.QLabel(Dialog)
        font = QtGui.QFont()
        font.setPointSize(10)
        self.label_5.setFont(font)
        self.label_5.setObjectName("label_5")
        self.verticalLayout_4.addWidget(self.label_5)
        self.horizontalLayout_2.addLayout(self.verticalLayout_4)
        self.verticalLayout_5 = QtWidgets.QVBoxLayout()
        self.verticalLayout_5.setObjectName("verticalLayout_5")
        self.lineEditAssetReturn = QtWidgets.QLineEdit(Dialog)
        self.lineEditAssetReturn.setObjectName("lineEditAssetReturn")
        self.verticalLayout_5.addWidget(self.lineEditAssetReturn)
        self.lineEditAssetRisk = QtWidgets.QLineEdit(Dialog)
        self.lineEditAssetRisk.setObjectName("lineEditAssetRisk")
        self.verticalLayout_5.addWidget(self.lineEditAssetRisk)
        self.horizontalLayout_2.addLayout(self.verticalLayout_5)
        self.verticalLayout_6.addLayout(self.horizontalLayout_2)
        self.horizontalLayout_3 = QtWidgets.QHBoxLayout()
        self.horizontalLayout_3.setObjectName("horizontalLayout_3")
        self.pushButtonCalculate = QtWidgets.QPushButton(Dialog)
        self.pushButtonCalculate.setObjectName("pushButtonCalculate")
        self.horizontalLayout_3.addWidget(self.pushButtonCalculate)
        self.pushButtonClear = QtWidgets.QPushButton(Dialog)
        self.pushButtonClear.setObjectName("pushButtonClear")
        self.horizontalLayout_3.addWidget(self.pushButtonClear)
        self.verticalLayout_6.addLayout(self.horizontalLayout_3)
        self.labelDisplayResult = QtWidgets.QLabel(Dialog)
        font = QtGui.QFont()
        font.setPointSize(12)
        font.setBold(True)
        font.setWeight(75)
        self.labelDisplayResult.setFont(font)
        self.labelDisplayResult.setObjectName("labelDisplayResult")
        self.verticalLayout_6.addWidget(self.labelDisplayResult)
        self.verticalLayout_7.addLayout(self.verticalLayout_6)

        self.retranslateUi(Dialog)
        QtCore.QMetaObject.connectSlotsByName(Dialog)

    def retranslateUi(self, Dialog):
        _translate = QtCore.QCoreApplication.translate
        Dialog.setWindowTitle(_translate("Dialog", "Dialog"))
        self.label.setText(_translate("Dialog", "Enter the numbers of assets:"))
        self.label_2.setText(_translate("Dialog", "Enter the risk free rate of return: "))
        self.labelIthAsset.setText(_translate("Dialog", "Seperated by space, enter each individual returns & risks"))
        self.label_4.setText(_translate("Dialog", "Enter the asset return:"))
        self.label_5.setText(_translate("Dialog", "Enter the asset risk:"))
        self.pushButtonCalculate.setText(_translate("Dialog", "Calculate"))
        self.pushButtonClear.setText(_translate("Dialog", "Clear"))
        self.labelDisplayResult.setText(_translate("Dialog", "Results displayed"))


if __name__ == "__main__":
    import sys
    app = QtWidgets.QApplication(sys.argv)
    Dialog = QtWidgets.QDialog()
    ui = Ui_Dialog()
    ui.setupUi(Dialog)
    Dialog.show()
    sys.exit(app.exec_())

# On a different python file save the code below


from PyQt5.QtWidgets import QDialog, QApplication
import sys
from financial_assets_allocation import *
import math
import numpy as np


class MyForm(QDialog):
    def  __init__(self):
        super().__init__()
        self.ui = Ui_Dialog()
        self.ui.setupUi(self)
        
        self.ui.pushButtonCalculate.clicked.connect(self.assets_allocation_func)
        self.show()
        self.ui.pushButtonClear.clicked.connect(self.clearing_content)
    
    
    def clearing_content(self):
        self.ui.labelDisplayResult.clear()
        self.ui.lineEditNumbersOfAssets.clear()
        self.ui.lineEditRiskFreeRateOfReturn.clear()
        self.ui.lineEditAssetReturn.clear()
        self.ui.lineEditAssetRisk.clear()
             
        
    def assets_allocation_func(self):
        size = self.ui.lineEditNumbersOfAssets.text()
        size = int(size)
        risk_free_rate_of_return = self.ui.lineEditRiskFreeRateOfReturn.text()
        risk_free_rate_of_return = float(risk_free_rate_of_return)
        
    
        ith_returns = self.ui.lineEditAssetReturn.text()
        ith_returns = list(map(float, ith_returns.strip().split()))[:size]
        ith_variances = self.ui.lineEditAssetRisk.text()
        ith_variances = list(map(float, ith_variances.strip().split()))[:size]
    
        assets_list = list()
        for i in range(size):
            sharpe = (ith_returns[i] - risk_free_rate_of_return)/math.sqrt(ith_variances[i])
            assets_list.append(sharpe)
        allocation_list = list()
        for j in range(len(assets_list)):
            allocation_list.append(assets_list[j]/sum(assets_list))
        self.ui.labelDisplayResult.setText(f"Allocate: {np.round(allocation_list,2)}") 
        

if __name__ == "__main__":
    app = QApplication(sys.argv)
    w = MyForm()
    w.show()
    sys.exit(app.exec_())
