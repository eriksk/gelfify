# Gelfify - log4net Gelf Appender

Currently supports

* TCP
* UDP

## Features

* Works with .NET 3.5
* Json objects
* Additional parameters (set in config)

## Appenders

	UDPAppender - Gelfify.Appenders.UDPAppender
	TCPAppender - Gelfify.Appenders.TCPAppender

## Layouts

	GelfLayout - Gelfify.Layouts.GelfLayout

## Usage

Configure appenders for log4net in your Web.config or log4net.config (check log4net docs for more details)


	<log4net>
	  <appender name="UDPAppender" type="Gelfify.Appenders.UDPAppender, Gelfify">
	    <remoteAddress value="127.0.0.1" />
	    <remotePort value="12201" />

	    <layout type="Gelfify.Layouts.GelfLayout, Gelfify">
	      <param name="AdditionalFields" value="Application:Gelfify.Console, Environment:Dev" />
	    </layout>
	  </appender>

	  <appender name="TCPAppender" type="Gelfify.Appenders.TCPAppender, Gelfify">
	    <remoteAddress value="127.0.0.1" />
	    <remotePort value="12201" />

	    <layout type="Gelfify.Layouts.GelfLayout, Gelfify">
	      <param name="AdditionalFields" value="Application:Gelfify.Console, Environment:Dev" />
	    </layout>
	  </appender>

	  <root>
	    <level value="INFO" />
	    <appender-ref ref="UDPAppender" />
	    <appender-ref ref="TCPAppender" />
	  </root>
	</log4net>
