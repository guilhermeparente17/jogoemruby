def da_boas_vindas
	puts "Bem vindo ao jogo"
	puts "Bem viaod ao mundo de Eldoor\nVocê é um guerreiro do reino de Eldin e terá que salvar a princesa Vandin"
	puts "Você atacara com a sua sorte em numeros randomicos de 0 a 100 de dano. Boa sorte"
end	

def intro 
	puts "Voce esta no castelo de Eldin e a princesa esta sob vigia de 3 orcs"
	puts "Voce tem uma espada e um escudo, se voce nao der mais de 150 de dano nos orcs você morrerá"
	puts "Se você nao defender mais de 100 de danos dos orcs, você morrerá"
	puts "BOA SORTE!!!"
end	

def limpar_tela
	system("cls")
end	

def parar_tela
	system("pause")
end	

def ataque_orc
	tentativas = 3
	vida_orc = 150
	pontos_ataque = 0
	puts "Voce terá 3 tentativas para tirar pelo menos 150 de vida do orc"
		for i in 1..tentativas
			puts "Voce ataca o orc..."
			parar_tela
			limpar_tela
			ataque = rand(100)
			pontos_ataque += ataque
			puts "Voce atacou o orc com #{ataque} de dano"
			puts "Voce ja alcançou #{pontos_ataque}"
			vida_orc -= ataque
			if pontos_ataque >= 100 
				puts "Voce derrou o orc"
				return
			end	
			
		end
		if pontos_ataque < 100
					puts "Voce morreu!"
					exit
			end	
end


def defesa_orc
	tentativas = 3
	vida_do_orc = 100
	pontos_defesa = 0
	puts "Voce terá 3 tentativas para defender pelo menos 100 de dano do orc, se conseguir, você eliminara o orc"
		for i in 1..tentativas
			puts "Voce defende o ataque do orc..."
			parar_tela
			limpar_tela
			dano_do_orc = rand(80)
			pontos_defesa += dano_do_orc
			puts "Voce defendeu o ataque com #{dano_do_orc} pontos de defesa"
			puts "Voce ate agora defendeu #{pontos_defesa}"
			vida_do_orc -= dano_do_orc
			if pontos_defesa >= 100
				puts "Voce defendeu o ataque do orc e eliminou o seu oponente"
				limpar_tela
				return
			end
		end	

			if pontos_defesa < 100
					puts "Voce morreu!"
					exit
			end	
end	

def op_orc(op)
	if op == 1 
		ataque_orc
		return
	end	

	if op == 2
		defesa_orc
		return
	end	

end

def escape_atq
	puts "Voce tera que conseguir mais de 100 pontos em uma so tentativa"
	puts "Buscando pontos para conseguir dar um rolamento..."
	parar_tela
	limpar_tela
	pontos = rand(200)
	puts "Voce conseguiu #{pontos} para o rolamento"
	if pontos >= 100
		puts "Voce conseguiu escapar do ataque do orc com um rolamento incrível"
		parar_tela
		limpar_tela
		return
	end
	if pontos < 100
		puts "O orc te matou, você morreu!"
		exit
	end	
end	

#Aqui começa o programa



#chamando a funçao da_boas_vindas
da_boas_vindas

puts "Digite seu nome"
nome = gets.strip
puts "\n\n"
puts "Seu nome é #{nome}\n\n"
parar_tela
limpar_tela


#chamando a funçao intro
intro

parar_tela
limpar_tela

puts "O primeiro orc surge na sua frente"
puts "Você deseja atacar ou defender? 1 - para atacar ou 2 -para defender"
op = gets.to_i


op_orc op
parar_tela
limpar_tela
puts "O segundo orc aparece por trás de você, dê um rolamento e escape de seu ataque"

escape_atq

puts "O segundo orc surge na sua frente"
puts "Você deseja atacar ou defender? 1 - para atacar ou 2 -para defender"
op = gets.to_i
op_orc op
parar_tela
limpar_tela

puts "Parabéns, você esta indo bem, concentre-se, so falta um orc para você salvar a princesa!"
puts "...\n"

parar_tela
limpar_tela

puts "O terceiro orc esta vindo, prepare-se..."

puts "O terceiro orc surge na sua frente"
puts "Você deseja atacar ou defender? 1 - para atacar ou 2 -para defender"
op = gets.to_i
op_orc op

puts "Parabéns, você concluiu o jogo, jovem guerreiro #{nome}"
parar_tela


