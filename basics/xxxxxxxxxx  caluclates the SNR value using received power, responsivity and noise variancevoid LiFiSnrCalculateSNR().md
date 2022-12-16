```
// caluclates the SNR value using received power, responsivity and noise variance
void LiFiSnr::CalculateSNR() {

	NS_LOG_FUNCTION(this);
	if (noise_var != 0)

{
//Pr =  1.9428e-06/*1.78935e-06*/;
 //noise_var = 4.59289e-15;
SNR = std::pow((Pr * res), 2) / noise_var;
//std::cout<<"SNR "<<SNR<<" res "<<res<<" noise_var "<<noise_var<<std::endl;
}
}

LiFiSnr>().AddAttribute("PowerReceived",
					"average received optical signal power", DoubleValue(0),
					MakeDoubleAccessor(&LiFiSnr::Pr),
```

