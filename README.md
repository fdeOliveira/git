<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>Contato</title>
<link href="css/estilo_cont.css" rel="stylesheet" type="text/css" />
</head>
<body bgcolor="#F7F7F7">
            
<div id="base_topo">
              
<!--Inicio da nav Menu--> 
              <nav id="menu">
               <ul>
                 <li><a href="home.php">HOME</a></li>
                    <li><a href="produtos.php">PRODUTOS</a></li>
                      <li><a href="servicos.php">SERVIÇOS</a></li>
                      <li><a href="parceiros.php">PARCEIROS</a></li>
                    <li><a href="sobre.php">SOBRE</a></li>
                 <li><a href="contato.php">CONTATO</a></li>
               </ul>
</nav><!--Fim nav Menu-->

               <div class="redesocial">
               <div class="face"><a href="https://www.facebook.com/pages/Lothus-Informatica/291038530936720?ref=bookmarks" target=_blank><img src="imagens/face.png" /></a></div>
                <div class="youtube"><a href="https://www.youtube.com/?gl=BR&hl=PT" target=_blank ><img src="imagens/youtube.png" /></a></div>
            
</div><!--Fim da div Rede Social--> 
</div><!--Fim da div Base_Topo-->

               <div class="base_geral">  
               <div class="base_box">              
               
<!--Inicio do mapa-->
                <div id="base_mapa"><img src="imagens/base_mapa.png" />
               <div class="mapa"><iframe src=     "https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1992.8799204979512!2d-44.19557600000002!3d-2.5845179999999943!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x7f69a41f684e6eb%3A0x79edd2614178a566!2sLothus+Inform%C3%A1tica!5e0!3m2!1spt-BR!2sbr!4v1420679745568" width="905" height="208"               frameborder="0" style="border:0"></iframe>
               </div>
                </div>
<!--Fim do mapa-->

<!--Inicio da Base_Descrição-->

                  <h1>LOCALIZAÇÃO</h1>
                <h2>LOTHUS INFORMÁTICA</h2>
              <h3>CENTRAL DE ATENDIMENTO</h3>
               <div class="base_descricao" >    
               <div class="endereco">
                    Rua:. 16, Nº 02, Qd 17 <br/>
                    CEP:. 65058-309 <br />
                    Jardim América - São Luis | MA <br />
                    Telefone:. (98) 3247-5043 
                    <br /><br /><br />
                    &bull; COMERCIAL <br />
                    (98) 98812-0575 <br />
                    elias@lothusinformarica.com.br <br /><br />
                    &bull; SUPORTE <br />
                    (98) 99902-3858 <br />
                    suporte@lothusinformarica.com.br <br /><br />
                    &bull; JURÍDICO <br />
                    (98) 98724-7753 <br />
                    juridico@lothusinformarica.com.br <br />
               </div>
               
               <!--Inicio do formulario de contato-->
               
               <form id="form_contato" action="home.php" method="post" enctype="multipart/form-data" >
               <div class="esquerda">
               <label>Nome:.</label>
               <input type="text" class="input_contato" name="nome"required />
               <label>E-mail:.</label>
               <input type="email" class="input_contato" name="email" required />
               <label>Assunto:.</label>
               <input type="text" class="input_contato" name="assunto" required />
               </div>
               <div class="direita">
               <label>Mensagem:.</label>
               <textarea name="mensagem" required /> </textarea>
               <input type="submit" value="Enviar Mensagem" name="enviar"  class="btn_contato"/>
               
               </div>
               </form>   
               
               <?php
			   if (isset($_POST['enviar'])){
			   
			   $nome     = utf8_decode ($_POST['nome']);
			   $email    = utf8_decode ($_POST['email']);
			   $assunto  = utf8_decode ($_POST['assunto']);
			   $mensagem = utf8_decode ($_POST['mensagem']);
			   $assuntoemail = 'Mensagem enviada atravez do site Lothus Informática';

   $subject  =  '=?UTF-8?B?'.base64_encode($assuntoemail).'?='; // pega os dados que foram digitados no id subject.
   $headers  = "From: $email\r\n";
   $headers .= "Reply-to: $email\r\n";
   $headers .= "Content-type:text/html; charset=iso-8859-1";

/*abaixo são os dados que serão enviados para o email cadastrado para receber o formulário.*/

   $corpo  = '<b>Mensagem Enviada:</b><br>';
   $corpo .= '<b>Nome:</b> '. $nome . '<br>';
   $corpo .= '<b>Email do Remetente:</b> '. $email . '<br>';
   $corpo .= '<b>Assunto: </b>' . $assunto . '<br>';
   $corpo .= '<b>Mensagem:</b><br>' . $mensagem . '<br>';

   $email_to = 'fernando86oliveira@live.com'; 
   $status = mail($email_to, $subject, $corpo, $headers); //Enviando o email.

   if($status) {
        echo "<script> alert('Mensagem enviada com sucesso.'); </script>"; //Verifica se o email foi enviado com sucesso.
   }
   else {
        echo "<script> alert('Falha ao enviar mensagem. Tente novamente.');</script>"; //Mensagem de erro ao enviar o email.
   }
   echo "<script> window.location.href = 'contato.php'; </script>"; //Aqui vai a pagina de redirecionamento depois do email enviado.
   }
?>    

</div><!--Fim da div class Descrição-->
</div><!--Fim da div class Base_descricao-->
</div><!--Fim da div class Base_SysComercial-->                                   
</div><!--Fim da div class Base_Geral-->

<!--Inicio do Rodapé-->
                 <div class="rodape">
                    <div class="rodape_menu">
                      <ul>
                   <li><a href="sobre.php">Empresa</a></li>
                   <li><a href="servicos.php">Serviços</a></li>
                   <li><a href="parceiros.php">Parceiros</a></li>
                   <li><a href="contato.php">Trabalhe Conosco</a></li>
                   <li><a href="contato.php">Contato</a></li>
                      </ul>
                     <div id="rodape_text">Copyright &copy 2010 - 2014  Todos os Direitos Reservados.</div>
                     </div>
                   </div>

<!--Fim do Rodapé-->

</body>
</html>
