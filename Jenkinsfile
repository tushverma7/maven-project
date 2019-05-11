Pipeline{

agent any{

Stages{
	Stage ('SCM Checkout'){
	git 'Github URL'
}

	Stage ('compile soure code'){
	Steps{
		with maven (maven : 'mymaven'){
		sh 'mvn compile'
}
}
}

Stage ('Test'){
Steps{

	Juint
}
}

Stage ('Package Source Code'){
Steps{
	sh 'mvn package'
}
}

Stage ('Install the Source Code'){
Steps{
	sh 'mvn Install'
}
}
}
}
}
